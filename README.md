# Cinema App
This is simple cinema service application for booking tickets, with registration, authentication and CRUD operations. 

## Features:
- Registration and Authentication of User
- Adding the new movies, cinema halls
- Creating, updating, deleting movie session
- Searching available movie sessions
- Completing the shopping cart
- Making the order
- Getting the history of orders

## Project structure:
```bash
my-cinema-map
│   
├───src 
│   ├───main
│   │   ├───java
│   │   │   └───cinema
│   │   │       ├───config
│   │   │       │       AppConfig.java
│   │   │       │       DataInitializer.java
│   │   │       │       SecurityConfig.java
│   │   │       │       SecurityInitializer.java
│   │   │       │       WebAppInitializer.java
│   │   │       │       WebConfig.java
│   │   │       │
│   │   │       ├───controller
│   │   │       │       AuthenticationController.java
│   │   │       │       CinemaHallController.java
│   │   │       │       CustomGlobalExceptionHandler.java
│   │   │       │       MovieController.java
│   │   │       │       MovieSessionController.java
│   │   │       │       OrderController.java
│   │   │       │       ShoppingCartController.java
│   │   │       │       UserController.java
│   │   │       │
│   │   │       ├───dao
│   │   │       │   │   AbstractDao.java
│   │   │       │   │   CinemaHallDao.java
│   │   │       │   │   MovieDao.java
│   │   │       │   │   MovieSessionDao.java
│   │   │       │   │   OrderDao.java
│   │   │       │   │   RoleDao.java
│   │   │       │   │   ShoppingCartDao.java
│   │   │       │   │   TicketDao.java
│   │   │       │   │   UserDao.java
│   │   │       │   │
│   │   │       │   └───impl
│   │   │       │           CinemaHallDaoImpl.java
│   │   │       │           MovieDaoImpl.java
│   │   │       │           MovieSessionDaoImpl.java
│   │   │       │           OrderDaoImpl.java
│   │   │       │           RoleDaoImpl.java
│   │   │       │           ShoppingCartDaoImpl.java
│   │   │       │           TicketDaoImpl.java
│   │   │       │           UserDaoImpl.java
│   │   │       │
│   │   │       ├───dto
│   │   │       │   ├───request
│   │   │       │   │       CinemaHallRequestDto.java
│   │   │       │   │       MovieRequestDto.java
│   │   │       │   │       MovieSessionRequestDto.java
│   │   │       │   │       UserRequestDto.java
│   │   │       │   │
│   │   │       │   └───response
│   │   │       │           CinemaHallResponseDto.java
│   │   │       │           MovieResponseDto.java
│   │   │       │           MovieSessionResponseDto.java
│   │   │       │           OrderResponseDto.java
│   │   │       │           ShoppingCartResponseDto.java
│   │   │       │           UserResponseDto.java
│   │   │       │
│   │   │       ├───exception
│   │   │       │       DataProcessingException.java
│   │   │       │
│   │   │       ├───lib
│   │   │       │       EmailValidator.java
│   │   │       │       FieldsValueMatch.java
│   │   │       │       FieldsValueMatchValidator.java
│   │   │       │       ValidEmail.java
│   │   │       │
│   │   │       ├───model
│   │   │       │       CinemaHall.java
│   │   │       │       Movie.java
│   │   │       │       MovieSession.java
│   │   │       │       Order.java
│   │   │       │       Role.java
│   │   │       │       ShoppingCart.java
│   │   │       │       Ticket.java
│   │   │       │       User.java
│   │   │       │
│   │   │       ├───security
│   │   │       │       CustomUserDetailsService.java
│   │   │       │
│   │   │       ├───service
│   │   │       │   │   AuthenticationService.java
│   │   │       │   │   CinemaHallService.java
│   │   │       │   │   MovieService.java
│   │   │       │   │   MovieSessionService.java
│   │   │       │   │   OrderService.java
│   │   │       │   │   RoleService.java
│   │   │       │   │   ShoppingCartService.java
│   │   │       │   │   UserService.java
│   │   │       │   │
│   │   │       │   ├───impl
│   │   │       │   │       AuthenticationServiceImpl.java
│   │   │       │   │       CinemaHallServiceImpl.java
│   │   │       │   │       MovieServiceImpl.java
│   │   │       │   │       MovieSessionServiceImpl.java
│   │   │       │   │       OrderServiceImpl.java
│   │   │       │   │       RoleServiceImpl.java
│   │   │       │   │       ShoppingCartServiceImpl.java
│   │   │       │   │       UserServiceImpl.java
│   │   │       │   │
│   │   │       │   └───mapper
│   │   │       │           CinemaHallMapper.java
│   │   │       │           MovieMapper.java
│   │   │       │           MovieSessionMapper.java
│   │   │       │           OrderMapper.java
│   │   │       │           RequestDtoMapper.java
│   │   │       │           ResponseDtoMapper.java
│   │   │       │           ShoppingCartMapper.java
│   │   │       │           UserMapper.java
│   │   │       │
│   │   │       └───util
│   │   │               DateTimePatternUtil.java
│   │   │
│   │   └───resources
│   │           db.properties
│   │
│   └───test
│       └───java
│
│   .gitignore
│   checkstyle.xml
│   pom.xml
│   README.md
```

## Endpoints
| Method type: | URL:                           | Description:                        | Access:    |
|--------------|--------------------------------|-------------------------------------|------------|
| POST         | /register                      | Registration of new user            | all        |
| GET          | /cinema-halls                  | Get all existing cinema halls       | user/admin |
| POST         | /cinema-halls                  | Add new cinema hall                 | admin      |
| GET          | /movies                        | Get all existing movies             | user/admin |
| POST         | /movies                        | Add new movie                       | admin      |
| GET          | /movie-sessions/available      | Get available movie sessions        | user/admin |
| POST         | /movie-sessions                | Add new movie session               | admin      |
| PUT          | /movie-sessions/{id}           | Update existing movie session       | admin      |
| DELETE       | /movie-sessions/{id}           | Delete movie session                | admin      |
| GET          | /orders                        | Get order history                   | user       |
| POST         | /orders/complete               | Complete the order                  | user       |
| PUT          | /shopping-carts/movie-sessions | Add movie session to shopping cart  | user       |
| GET          | /shopping-carts/by-user        | /Get contains of the shopping cart  | user       |
| GET          | /users/by-email                | Find user by email                  | admin      |

## Technologies
+ Java 17
+ Spring 5.3.20
+ Spring Security 5.6.10
+ Hibernate 5.6.14.Final
+ REST API
+ Apache Tomcat 9.0.65
+ MySQL

## Instructions to run the project:
To start this project you need to do next steps:

1. Install and configure Apache Tomcat 9.0.65
2. Install MySQL and MySQL Workbench
3. Create the clear schema for the project
4. Set credentials of your MySQL DB in "src/main/resources/db.properties"
5. Add new run configuration in IDEA:
Run -> Edit configurations... -> Add new run configuration... -> Tomcat Server -> Local -> Fix -> Select "my-cinema-app:war exploded" (In graph "Application context" must be the only "/")
6. Run.
