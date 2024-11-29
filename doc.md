```
@Entity
@Table(name = "app_user")
@Data
@NoArgsConstructor
@AllArgsConstructor
@Builder
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @Column(nullable = false, unique = true)
    private String username;

    @Column(nullable = false)
    private String password;

    @Column(nullable = false)
    private LocalDateTime createdAt;

    @Column(nullable = false)
    private String roles;

    @OneToMany(mappedBy = "user", cascade = CascadeType.ALL, orphanRemoval = true)
    private List<TravelPlan> travelPlans;

    @OneToMany(mappedBy = "user", cascade = CascadeType.ALL, orphanRemoval = true)
    private List<TravelRecord> travelRecords;

}


@Configuration

public class SecurityConfig {
    @Bean
    public PasswordEncoder passwordEncoder() {
        return new BCryptPasswordEncoder();
    }
}


@Entity
@Data
@NoArgsConstructor
@AllArgsConstructor
@Builder
public class TravelRecord {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @ManyToOne
    @JoinColumn(name = "user_id", nullable = false)
    private User user;

    private String title;
    private String description;
    private String imageUrl;
    @Builder.Default
    private LocalDateTime createdAt = LocalDateTime.now();
}


@Entity
@Data
@NoArgsConstructor
@AllArgsConstructor
@Builder
public class TravelRecommendation {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String companionType;
    private String moodType;
    private String seasonType;
    private String title;
    private String description;
    private String imageUrl;
}



@Entity
@Data
@NoArgsConstructor
@AllArgsConstructor
@Builder
public class TravelPlan {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @ManyToOne
    @JoinColumn(name = "user_id", nullable = false)
    private User user;

    private LocalDate startDate;
    private LocalDate endDate;
    private String title;
    private String description;

    @OneToMany(mappedBy = "travelPlan", cascade = CascadeType.ALL, orphanRemoval = true)
    private List<TravelPlanDetail> travelPlanDetails;
}


	User
		+------------------+
		| user_id (PK)     |
		| username         |
		| password         |
		| created_at       |
		| updated_at       |
		+------------------+
		          |
		          | 1
		          |----< TravelPlan
		          |                |
		          |                | 1
		          |                |----< TravelPlanDetail
		          |
		          | 1
		          |----< TravelRecord
		          |
		          | 0..1
		          |----< TravelRecommendation
		          
		TravelPlan
		+-----------------------+
		| plan_id (PK)          |
		| user_id (FK)          |
		| title                 |
		| description           |
		| start_date            |
		| end_date              |
		| created_at            |
		| updated_at            |
		+-----------------------+

		TravelPlanDetail
		+-----------------------+
		| detail_id (PK)        |
		| plan_id (FK)          |
		| date                  |
		| time_slot             |
		| activity              |
		+-----------------------+

		TravelRecord
		+-----------------------+
		| record_id (PK)        |
		| user_id (FK)          |
		| title                 |
		| description           |
		| image_url             |
		| created_at            |
		| updated_at            |
		+-----------------------+

		TravelRecommendation
		+-----------------------+
		| recommendation_id (PK)|
		| user_id (FK, optional)|
		| companion_type        |
		| mood_type             |
		| season_type           |
		| title                 |
		| description           |
		| image_url             |
		+-----------------------+

```
