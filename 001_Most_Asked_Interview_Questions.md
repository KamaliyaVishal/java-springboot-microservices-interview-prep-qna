# Interview Questions (Merged, Questions Only)

Merged from asked rounds and the most-asked list. Duplicates removed. No answers. No company names.

---

## 1. Core Java

1. Difference between JDK, JRE, and JVM?
2. Explain JVM architecture and its internal components.
3. How does `javac` differ from the `java` command? What happens when you run `java HelloWorld`?
4. Difference between JIT compilation and AOT compilation? Have you used GraalVM Native Image?
5. Explain Heap vs Stack vs Metaspace.
6. What caused PermGen issues, and how did Metaspace change that?
7. Explain Young Gen, Old Gen, Eden, and Survivor spaces.
8. What causes `StackOverflowError` vs `OutOfMemoryError`?
9. What is a memory leak in Java, and how do you prevent it?
10. How would you troubleshoot and resolve an `OutOfMemoryError` in production?
11. How do you capture and analyze a heap dump safely in production?
12. Describe JVM memory areas and where local, instance, static variables, and objects are stored.
13. Compare G1GC, ZGC, and Shenandoah. When would you pick each?
14. How do you find the exact line of Java code causing 100% CPU?
15. How do you identify Virtual Thread pinning issues in Java 21?
16. Why is `String` immutable, and how do you create your own immutable class?
17. What are Records, and when should you use them instead of POJOs?
18. Records only guarantee shallow immutability — what does that mean, and how do you fix it?
19. What is the contract between `equals()` and `hashCode()`?
20. Can two different objects generate the same hash code? What happens then?
21. What catastrophic bugs occur in a `HashMap`/`HashSet` if the equals/hashCode contract is violated?
22. Why should you avoid using JPA entities as HashMap keys?
23. What is a marker interface, and where have you used one?
24. Difference between `String`, `StringBuilder`, and `StringBuffer`?
25. How does string concatenation with `+` work in modern Java vs `String.join`?
26. Difference between `==` and `.equals()`?
27. Can you override a private method?
28. Difference between abstract class and interface? How do you decide which to use?
29. After default methods, are interfaces still 100% abstract?
30. Can an implementing class object be referenced using an interface type?
31. What are default methods, and why were they introduced?
32. Explain static polymorphism vs dynamic polymorphism.
33. If only the return type of a method is changed, is that overloading? Why or why not?
34. How do you create a custom exception? When do you extend checked vs unchecked exceptions?
35. What are the performance implications of throwing exceptions?
36. What does it mean to swallow an exception, and why is it dangerous?
37. How does try-with-resources handle suppressed exceptions?
38. Difference between fail-fast and fail-safe iterators?
39. Difference between `Comparable` and `Comparator`?
40. Difference between `volatile` and `transient`?
41. Difference between `volatile`, atomic classes, and `synchronized`?
42. Why don't Java Collections always implement `Serializable` by default in a useful way?
43. What are atomic classes, and why are they used?
44. How do `AtomicInteger` and CAS achieve thread safety without locks? What is the downside under high contention?
45. When would you use `LongAdder` instead of `AtomicInteger`?
46. What is serialization? Which keyword skips a field?
47. How do you create a custom annotation?
48. Explain SOLID principles with Java examples.
49. Common Java design patterns you have used?
50. Singleton — how do you implement it correctly (and why double-check locking / enum)?
51. Builder pattern — how do you implement it? Can it be used with constructors?
52. Difference between Proxy and Decorator patterns?
53. What is the DAO pattern, and why is it still useful?
54. Can a functional interface extend another interface?
55. Give an example of a functional interface. What are Predicate, Consumer, and Supplier?
56. What are Java Streams, and what are their advantages?
57. Which is faster: loops or Stream API? When would you not use streams?
58. How do you implement custom collectors in Streams, and why would you need them?
59. What happens if you reuse a Stream after a terminal operation (`count()` then `forEach()`)?
60. Stream API improvements from Java 8 to Java 21?
61. How would you design a system where Java 17+ sealed classes give a real advantage?
62. Approach for migrating an application from Java 17 to Java 21/25?
63. Important things to consider while upgrading Java versions with Spring Boot 3.x?
64. New features you actually use in Java 8, 17, and 21?
65. Difference between `submit()` and `execute()` on `ExecutorService`?
66. What is `CompletableFuture`, and how do you use it?
67. How do exceptions propagate in `CompletableFuture` / `ExecutorService`, and how do you avoid losing them?
68. What is multithreading, and how have you used it in production?
69. Difference between `synchronized` and `volatile` in terms of the Java Memory Model?
70. What is a Thread Pool Starvation Deadlock, and how do you prevent it?
71. How do you systematically prevent deadlocks, and how do you diagnose them in production?
72. What is a `ReentrantLock` vs `synchronized`?
73. What is a `ReadWriteLock`, and when would you use it?
74. Explain StampedLock and optimistic reads.
75. Fair vs non-fair locks — when would you configure fairness?
76. Intrinsic vs explicit locks; biased / lightweight / heavyweight locks in HotSpot?
77. Are Spring beans thread-safe by default?
78. Difference between `HashMap` and `ConcurrentHashMap`?
79. Can you insert a null key into a `ConcurrentHashMap`? Why?
80. How is `ConcurrentHashMap` faster than `Hashtable`?
81. How does `ConcurrentHashMap` achieve high throughput in Java 8+?
82. What will be the size of a HashMap after inserting two null keys?
83. What will be the size of a HashSet after adding the same String twice?
84. What will be the size of a HashSet after adding two different Employee objects with the same ID?
85. Can you remove elements from a Set while traversing it? What is the correct way?
86. Walk through a `HashMap.put()` in Java 8+ (hash spread, index, collision, treeification).
87. Relationship between initial capacity, load factor, and rehashing? Why pre-size maps?
88. Why must HashMap capacity be a power of two?
89. Risks of using a mutable object as a HashMap key?
90. Differences between HashMap, HashSet, LinkedHashMap, and ArrayList?
91. How do Java 21 Virtual Threads change the concurrency model vs platform threads?
92. Architectural implications of virtual threads for a Spring Boot 3.x high-throughput app?
93. Why should you not pool virtual threads?
94. Difference between Flux and Mono in Project Reactor?
95. When would you still choose WebFlux over virtual threads?
96. How do you find a memory leak in a running service?
97. How do you read a GC log, and what would make you change the collector?
98. How do you profile a slow endpoint in production without a restart?
99. What is false sharing, and how does it slow down concurrent code?
100. What does escape analysis change about allocation?
101. Virtual threads inside `synchronized`: what changed in JDK 24?
102. How do you size a thread pool for IO-bound vs CPU-bound work?
103. The executor queue is full. What happens, and which rejection policy do you pick?
104. `CompletableFuture`: which thread runs the callbacks, and why does it matter?
105. How do you sort a Map in Java?
106. What is try-with-resources?
107. What is a multi-catch statement in Java?
108. What is the difference between `Runnable` and `Callable`?
109. Explain the types of exceptions and the Exception hierarchy in Java.
110. Explain the OOP principles (encapsulation, inheritance, polymorphism, abstraction) with real-world examples.
111. How does Java Garbage Collection work from allocation to collection?
112. What are the new features introduced in Java 7, 8, 11, and 17?
113. What is the difference between the `final` keyword on a class/method vs a `final` variable?
114. How do you avoid performance issues caused by synchronization?
115. What is a `BlockingQueue`, and where do you use it in real applications?
116. What changes did you make when migrating from Java 7 to Java 8?
117. What are different ways to ensure thread safety?
118. What is `ThreadLocal`, and where is it used?
119. What is the difference between `HashMap` and `Hashtable`?
120. Why does `Hashtable` not allow null keys or values?
121. What is load factor in `HashMap`? What does the default 0.75 mean?
122. Explain Java Streams: lazy evaluation, intermediate vs terminal operations, and common pitfalls. How do you ensure performance and correctness?
123. Explain Java generics: type erasure, bounded wildcards, and invariance. How does that affect reusable utilities and DTO mapping?
124. How do you implement immutability in Java for thread-safe DTOs (final fields, defensive copies, equals/hashCode)?
125. Explain Java serialization/deserialization fundamentals and security risks. How do you prevent unsafe deserialization in REST services?
126. What is the Java Memory Model’s impact on thread-safety in concurrent microservices?
127. What are the different types of class loaders in Java?
128. Where are String pool and string literals stored?
129. What is the use of `finalize` in Java?
130. What is the difference between `final`, `finally`, and `finalize`?
131. What is the difference between `final` and `static`?
132. What are access modifiers in Java?
133. Is Java 100% object-oriented? Why or why not?
134. What is the difference between method overloading and method overriding?
135. Can we override a static method? Can a static method be overloaded?
136. Can we override the `main` method? Can we overload the `main` method?
137. What is an “IS-A” relationship and a “HAS-A” relationship? How do you implement them in Java?
138. Explain multi-level inheritance.
139. Can you override a default method?
140. Two interfaces have the same default method, and a class implements both. What happens?
141. Explain the interface diamond problem in Java.
142. What is a generic interface?
143. What is the Reflection API?
144. Why is `Comparator` a functional interface?
145. What is a lambda expression?
146. What is `Optional`? When should you use it, and why is it recommended?
147. What is the difference between `Optional.map()` and `Optional.flatMap()`?
148. How does `var` help with type inference?
149. How does pattern matching for `switch` improve readability in Java 17+?
150. What are text blocks, and how do they simplify working with JSON/XML?
151. How does the `String` class differ from other classes in Java?
152. What is the difference between a String object and a String literal?
153. What is the output of concatenating a String without assigning the result back?
154. How do you swap two strings without using a third variable?
155. You have an immutable `Employee` that holds a mutable `Department`. Does that break immutability? Why, and how do you fix it?
156. Can we add values into a `final` List? Why or why not?
157. How do you make a class non-inheritable? What is a `final` class?
158. Can a static class or static inner class be created in Java?
159. What are wrapper classes, and why were they introduced?
160. What are different ways to create objects in Java?
161. If a class has private data members, how can you access them?
162. What is recursion?
163. What is `System`, `out`, and `println` in `System.out.println()`?
164. What is the XOR operation in Java? Give a real-world example?
165. Explain copy-on-write in Java.
166. What is the difference between shallow copy, deep copy, and defensive copy?
167. Why is an array considered fixed-size, and how is `ArrayList` dynamic?
168. What is an `enum` in Java?
169. What are callback functions in Java?
170. What is Externalization in Java?
171. What is the use of `serialVersionUID` when a class implements `Serializable`?
172. What happens if you apply `transient` to a `byte` field?
173. If a Singleton is serialized, can its uniqueness break? How do you prevent that?
174. What is the difference between checked and unchecked exceptions?
175. What is the difference between errors and exceptions? Is `StackOverflowError` an error or an exception?
176. Give a list of common errors in Java.
177. What is exception chaining?
178. Can you write `try` without `catch`? Can you write only `try` and `finally`?
179. What is the difference between `throw` and `throws`?
180. A parent class method does not throw an exception, but the child class method throws one. Is that allowed? What type of exception can it throw?
181. What happens if you `return` from both `catch` and `finally`?
182. A class has `process(String a)` and `process(Object o)`. If you call `obj.process(null)`, which method is called?
183. How do you handle dynamic payloads without relying on strict Java POJOs?
184. What is the time complexity of `get` and `put` in a `HashMap`?
185. What is the difference between `HashMap` and `TreeMap`?
186. How is `ConcurrentHashMap` different from `Collections.synchronizedMap()`?
187. Which collection stores data in sorted order, and which stores data in insertion order?
188. How do you store only unique objects in a collection? How do you store objects in a Set sorted by a field?
189. How does a `ConcurrentModificationException` occur, and how do you avoid it?
190. What is the difference between `CopyOnWriteArrayList` and `ArrayList`?
191. What is the difference between `list.sort` and `Stream.sorted`?
192. Why might `List.of(...).sort()` throw `UnsupportedOperationException`?
193. What are Max Heap and Min Heap in Java? What is `PriorityQueue`?
194. How do you remove `HashMap` entries with unwanted values such as `null`, `"null"`, empty string, or whitespace?
195. What happens inside an `ArrayList` when we add or remove elements inside a `for` loop?
196. What is the difference between List, Set, and Map?
197. What is a method reference?
198. How do you create a functional interface and implement it?
199. What is the difference between `notify()` and `notifyAll()`?
200. Why are `wait()`, `notify()`, and `notifyAll()` in the `Object` class?
201. Can you run a thread by calling `run()` without `start()`? If not, why?
202. What is the difference between a process and a thread?
203. What happens when a synchronized method is called with different threads and different objects?
204. What is the difference between `volatile` and `static`?
205. What is a race condition?
206. Explain `Semaphore` in Java.
207. You started two task executions in two separate threads. How do you combine their results and print them?
208. What is the difference between `parallelStream` and `CompletableFuture`?
209. If you receive 100 login requests, how many service-layer objects are created with the default singleton bean?
210. If you are running two Java programs together, how do you know how many JVM instances have been created?
211. What is the Liskov Substitution Principle (LSP)?
212. What is the Factory design pattern and its usages?
213. What is the Strategy pattern?
214. What is the Proxy pattern in Spring?
215. What is AOP?
216. Explain aggregation vs composition in OOP.
217. Write code that demonstrates all OOP concepts in one class.
218. Constructor vs Builder: if you add more fields and do not want to set all of them, which pattern should you use?
219. What are the benefits of sealed classes introduced in Java 17?
220. `HashMap` with `equals()` always true and random `hashCode()` — what is `map.size()` after two puts?
221. Two `User` objects with the same name used as keys without overriding `equals`/`hashCode` — what does `get` return? What change makes it work?
222. A method parameter named `data` does not change the instance field `data` — what is the output?
223. Guess the program output on static blocks.
224. `final` field initialization snippets (uninitialized, assigned only in a method, mutating fields of a `final` object).
225. What is the output of `System.out.println` for an `int`, a String, and a custom object that does not override `toString()`?
226. Refactor a classic `switch` to Java 17 switch expressions.
227. What are `yield` and `join` in threads?
228. What are `FixedThreadPool` and `CachedThreadPool`?
229. What is the difference between the Executor framework and the `Runnable` interface?
230. Can a thread return a value? How (`Callable`, `CompletableFuture`)?
231. How do you complete an async task with `CompletableFuture`?
232. If a task needs to be performed faster, do you use parallel processing or multithreading?
233. How do you process millions of records in Java, and what different approaches can you use?
234. Explain how you design a high-throughput in-memory cache safely.
235. What is the difference between `map` and `flatMap` in streams?
236. How do you use Stream API with parallel streams / multi-threading?
237. Write a single line of Stream code to print all elements of an integer list.
238. From `List<Order>`, find `OrderDetails` whose quantity is not 0; create a map of id to totalAmount; find unique item names using `flatMap`.
239. From a list of integers, produce distinct sorted squares (example: `[8, 9, 4, 3, 10, 3, 5]` → `[9, 16, 25, 64, 81, 100]`).
240. Using streams, find employees whose age is greater than 50 and salary greater than 50000.
241. Using streams, find all subordinates of a specific manager.
242. Using streams, count employees by gender or role.
243. Using streams, find distinct departments from an employee list.
244. Using streams, find max from a list along with its count.
245. Find occurrences of each character using streams, preserving insertion order, then sort by frequency descending and alphabetically on ties.
246. Same character-count problem without Map and Stream.

---

## 2. Spring Core and Spring Boot

1. Explain Spring Dependency Injection and Inversion of Control.
2. Different ways to perform dependency injection?
3. Why is constructor injection preferred over field injection?
4. Why is `final` not allowed with field `@Autowired`?
5. Difference between `@Component` and `@Bean`? When do you use each?
6. Difference between `@Component`, `@Service`, `@Repository`, and `@Controller`?
7. Difference between `@Qualifier` and `@Primary`?
8. Difference between `@Value` and `@ConfigurationProperties`?
9. Two classes define beans with the same name. What happens, and how do you resolve it?
10. How many Spring containers are there, and what are they called?
11. Bean scopes in Spring? What is the prototype-into-singleton trap?
12. How do you inject a prototype or request-scoped bean into a singleton correctly?
13. Walk through the complete Spring bean lifecycle. Where do you intercept or proxy a bean?
14. How does Spring Boot auto-configuration work when `@SpringBootApplication` is parsed?
15. Commonly used Spring Boot annotations?
16. What does `@Transactional` do, and how does it work internally?
17. Which exceptions trigger automatic rollback: checked or unchecked?
18. Spring vs Jakarta `@Transactional` — which should you use, and why?
19. Transaction propagation types in Spring?
20. How do you handle distributed transactions across microservices?
21. How do you fetch users with Spring Data JPA? How do you run native queries?
22. How do you implement global exception handling?
23. How does `@ControllerAdvice` work under the hood?
24. What belongs in a production-grade API error payload? Why never return stack traces?
25. How do you map `MethodArgumentNotValidException` to field-level errors?
26. Danger of missing a catch-all exception handler?
27. How would you secure a REST API in Spring Boot?
28. How does Spring Security work internally?
29. What is a Security Filter Chain, and how does it work?
30. RBAC vs permission-based access — how do you implement both?
31. How would you secure a DELETE API?
32. How can Service C authorize a request from Service B when JWT is issued by Service A?
33. How do you implement OAuth 2.0? Grant types and when to use each?
34. Authentication vs authorization — how do you implement them?
35. Spring Boot profiles — what they are and how they work?
36. Why don't most Spring Boot apps use `@WebServlet`? How does DispatcherServlet work?
37. How do you implement pagination in Spring Boot?
38. How do you validate incoming requests?
39. How do you create a custom annotation in Spring Boot?
40. How does Spring Boot handle graceful shutdown in Kubernetes?
41. How do you detect and resolve HikariCP connection pool exhaustion?
42. HikariCP timeout with DB CPU under 30% — how do you diagnose?
43. What is Open Session in View, and why is it often disabled in production?
44. How do you implement CQRS in Spring Boot, and what are the trade-offs?
45. How do you implement caching with Spring (`@Cacheable`, eviction, Redis)?
46. Difference between `@RestController` and `@Controller`?
47. How do you write integration tests vs unit tests in Spring Boot?
48. What is `@SpringBootTest` vs `@WebMvcTest` vs `@DataJpaTest`?
49. How do you externalize configuration (env vars, Config Server, Azure App Config, AWS Parameter Store)?
50. How do you override auto-configuration?
51. Maven vs Gradle — why would you pick one?
52. Why is an application server needed if a web server can serve HTTP?
53. Lombok `@RequiredArgsConstructor` vs `@AllArgsConstructor` vs `@NoArgsConstructor`?
54. `spring.jpa.hibernate.ddl-auto` values and which are safe in production?
55. How would you design a Spring Boot app to fetch a list of students vs a single student?
56. How do you ensure a request is processed correctly end-to-end across services?
57. A Spring Boot service starts returning random 500s. Where do you begin?
58. How do you perform zero-downtime schema migrations with Spring Boot (Flyway/Liquibase)?
59. How would you guarantee a scheduled job runs only once across multiple instances?
60. How do you implement an idempotency layer for millions of requests per day?
61. How do you diagnose latency spikes caused by lock contention?
62. Are you using Actuator? Which endpoints and how do you secure them?
63. How do you customize Jackson ObjectMapper as a bean for a third-party library?
64. What is Spring Framework, and why do we use it?
65. What is the difference between Spring and Spring Boot?
66. How does Autowiring work in Spring?
67. What is Spring Security?
68. What is the difference between constructor injection and setter injection?
69. What happens if you do not use `@Autowired` in Spring?
70. How do you perform constructor injection without `@Autowired`?
71. What is a Maven build?
72. What does `mvn clean install` do?
73. How do you push code to production?
74. What is code coverage vs line coverage?
75. How do you improve code coverage when the build fails on coverage gates?
76. What are Spring Boot Starters, and why are they important?
77. What is `@SpringBootApplication`? What annotations does it include?
78. What is the difference between `@SpringBootApplication` and `@EnableAutoConfiguration`?
79. How do you create custom configuration in Spring Boot?
80. How do you handle complex nested configurations in Spring Boot?
81. How do you improve the startup time of a Spring Boot application?
82. How do you create a scalable Spring Boot application?
83. Can you use `@Component` and `@Service` interchangeably?
84. Can you use `@Configuration` and `@Component` interchangeably?
85. What happens if you apply both `@Service` and `@Repository` to the same class?
86. What are Spring stereotypes?
87. What is the difference between request and prototype bean scope?
88. Which bean scope is thread-safe?
89. What is `@PostConstruct`?
90. How do you resolve bean ambiguity without hardcoding a bean name in `@Qualifier`?
91. An interface `Payment` has `CardPayment` and `UPIPayment`. You autowire `Payment` without specifying which implementation. What happens?
92. What is the difference between `@ControllerAdvice` and `@ExceptionHandler`?
93. How do you handle and log exceptions in a Spring Boot application? How do you handle errors reported by a client?
94. How do you write event listeners in Spring Boot?
95. What is the use of conditional annotations in Spring?
96. How do you enable asynchronous method execution in Spring Boot?
97. How do you structure layers and packages (Controller, Service, Repository, Entity)? Explain the flow when creating APIs.
98. If the controller receives multiple requests at the same time, how would you handle them?
99. What is the difference between `@RequestParam` and `@PathVariable`?
100. What is the difference between `@RequestMapping` and `@GetMapping`?
101. How do you change a 200 response status to a custom status such as 201 or 202?
102. What is profiling in Spring Boot?
103. If two properties files have the same property, which one does Spring take?
104. Between `application.yml` and `application.properties`, which is loaded first? What is the difference between them?
105. Which annotations fetch a property from YAML?
106. How does Spring Boot handle embedded servers like Tomcat or Jetty?
107. How do you configure a datasource in Spring Boot? How is the database integrated?
108. What steps did you take to configure Redis cache? What get/set methods are available in Lettuce?
109. How do you manage language / i18n messages in Spring Boot?
110. How do you limit concurrent requests for an API?
111. What is a key vault in a Spring / cloud context?
112. Java HttpClient vs Apache HttpClient.
113. Different methods to call REST APIs from a Spring Boot microservice (`RestTemplate`, WebClient, Feign). What is the value of `name` in `@FeignClient`?
114. How does Spring Boot integrate with cloud services (for example AWS S3, RDS)?
115. How do you handle a vulnerable dependency in Maven?
116. What is isolation in Spring transactions?
117. Can we apply `@Transactional` at the class level?
118. What happens if you call a `@Transactional` method from another method in the same class?
119. A method is not annotated with `@Transactional` but is called from a method that is. If an error happens in the inner method, will rollback occur?
120. If you annotated with `@Transactional` but caught / handled exceptions, will rollback still work?
121. `@Transactional` vs explicit `save` and `commit`. Can a transaction still roll back after `save` and `commit`?

---

## 3. Spring Data JPA / Hibernate

1. What are ORM, JPA, Hibernate, and Spring Data JPA?
2. Do built-in Spring Data methods always return the full entity?
3. How do projections and custom JPQL fetch only selected columns?
4. Explain first-level cache vs second-level cache.
5. How does dirty checking work? When should you use `@Transactional(readOnly = true)`?
6. `CascadeType.REMOVE` vs `orphanRemoval = true`?
7. `@EmbeddedId` vs `@MapsId` vs `@JoinTable`?
8. Default lazy vs eager loading for associations?
9. What is `LazyInitializationException`, root cause, and how do you prevent it?
10. What is the N+1 problem, how do you detect it, and how do you fix it (`@EntityGraph`, JOIN FETCH, batch size)?
11. Optimistic vs pessimistic concurrency control?
12. How do you use `@Version` for optimistic locking?
13. Difference between `save()`, `saveAndFlush()`, and `persist()`?
14. How do you handle pagination consistently when rows are inserted/deleted between pages?
15. OFFSET/LIMIT pagination problems vs keyset/cursor pagination?
16. How do you model many-to-many with extra join-table columns?
17. How do you avoid `LazyInitializationException` in a REST layer without OSIV?
18. How would you map a composite primary key?
19. How do you write a native query that returns a DTO?
20. How do you handle schema evolution without locking out rolling deployments?
21. How do you define relationships between tables in Hibernate?
22. What are the types of relationships in Hibernate?
23. When using SQL Server or PostgreSQL with Spring Data JPA, how do you prevent N+1 queries and manage transaction boundaries for high-throughput services?
24. What is the difference between JPA and `JdbcTemplate`? When would you choose one over the other?
25. What is the difference between Hibernate and JPA?
26. How do you set up Hibernate in a Spring Boot project?
27. How many tables are needed for many-to-many mapping?
28. What is Session and `SessionFactory`?
29. What is the difference between `get` and `load` in Hibernate?
30. Explain Criteria API in Hibernate.
31. What is `@EntityGraph` in JPA?
32. What is the difference between `JpaRepository` and `CrudRepository`?
33. How do you fetch only one column from JPA?
34. What method name in JPA would you use to find an employee by name and birth date in a date range?
35. In JPA, if you use `findById` and no record is found, what is the output? Is an exception thrown?
36. How does a database connection pool work?
37. How do you define the relation between Employee and Salary entities in Hibernate?

---

## 4. REST APIs and Backend Design

1. What is REST, and how have you used it?
2. How would you design REST APIs that are scalable and follow REST conventions?
3. How do you version APIs?
4. How do you implement HATEOAS, and when is it worth it?
5. Idempotent HTTP methods — which are, and how do you make POST idempotent?
6. What is TPS, and how do you measure REST throughput?
7. How do you implement rate limiting?
8. REST vs gRPC — when do you choose each?
9. Sync vs async APIs — how do you decide?
10. How do you handle file uploads (including a 10 GB file)?
11. How do you design resumable uploads?
12. How do you document APIs (OpenAPI) and keep docs in sync?
13. How do you test a Java API for fault tolerance?
14. How do you test third-party integrations?
15. How do you handle concurrent requests safely?
16. Difference between stored procedure and function?
17. How do you optimize APIs when the DB query is already fast?
18. How do you implement request correlation / tracing IDs?
19. What is the difference between REST and SOAP?
20. What is a RESTful API?
21. What is the difference between HTTP and HTTPS?
22. REST, gRPC, or messaging between services: how do you choose?
23. How have you designed idempotent, retry-safe REST APIs for domain migrations using Spring Boot microservices?
24. What are the types of HTTP requests?
25. What is the difference between POST and PUT?
26. What is the difference between PUT and PATCH?
27. What is the HTTP OPTIONS method?
28. What is CORS?
29. What are common HTTP status codes?
30. Which HTTP status code would you return when a duplicate record is encountered?
31. How would you handle duplicate requests when a client retries an API call?
32. How would you design a standard REST API error response contract?
33. How do you send 1 million records as the response of an API call?
34. Suppose an API has rate limits and pagination. How would you perform a complete data backfill without missing or duplicating records?
35. Design a custom rate limiter that allows 120 requests within 1 minute.
36. REST vs SOAP. Which is better, and when?
37. Why is HTTPS more secure? What role does SSL/TLS play? Where is HTTPS mandatory?

---

## 5. Microservices and Distributed Systems

1. Advantages of microservices? Major challenges?
2. Monolith vs microservices — besides codebase split, what actually changes?
3. When would you choose a monolith vs microservices?
4. How do microservices communicate (sync and async) with examples?
5. What is an API gateway, and what is its role?
6. What is service discovery, and how does it work?
7. What is a circuit breaker, how does it work, and which library have you used?
8. If a downstream service returns HTTP 400, does the circuit breaker count it as failure?
9. How do you handle unresponsive downstream services?
10. Service A at 100% capacity, Service B at 50% — how do you prevent overload?
11. How do you prevent multiple requests from overloading servers?
12. How do you prevent duplicate/concurrent requests in a distributed transaction?
13. Order created and payment succeeded, inventory update failed — how do you handle it?
14. Saga types: choreography vs orchestration — when do you choose which?
15. When would you choose Saga orchestration over distributed transactions / 2PC?
16. What is the Outbox pattern, and how do you implement it for reliable event publishing?
17. What concurrency issues occur if the outbox worker is poorly written?
18. What is CQRS, and when is it worth the complexity?
19. How do you design cache invalidation across multiple microservices?
20. How do you prevent cache stampede, thundering herd, avalanche, and penetration?
21. How would you implement distributed locking without creating a bottleneck?
22. How do you secure service-to-service communication in a zero-trust architecture?
23. Edge authentication vs service-to-service authorization (JWT vs mTLS)?
24. How do you maintain consistency in a globally distributed Spring Boot system?
25. How would you guarantee exactly-once (or effectively-once) processing of events?
26. How do you implement backpressure in an event-driven architecture?
27. Scaling one microservice independently caused unexpected issues — what can go wrong?
28. Design patterns you have used in microservices?
29. Benefits of Redis vs hitting the primary database?
30. How do you ensure a particular request is processed correctly across the chain?
31. If one microservice goes down, how do you handle it?
32. How do you improve performance of a microservices application?
33. Design a high-level payment notification system using microservices.
34. How would you design an application from scratch (backend + frontend) step by step?
35. What is bulkhead pattern vs circuit breaker vs retry vs timeout vs fallback?
36. How do you implement distributed tracing?
37. How do you handle eventual consistency and user-visible stale reads?
38. How do you version events and APIs independently?
39. How do you split bounded contexts (DDD) in a real domain?
40. How do you do capacity planning for 10,000 TPS (app, network, DB, Kafka)?
41. How do you keep the database and Kafka consistent without 2PC?
42. A downstream service gets slow. How do you stop it taking yours down?
43. How do you ship a breaking schema change with zero downtime (DB and Kafka)?
44. When would you split a monolith, and when wouldn't you?
45. How have you modeled multi-tenant data in PostgreSQL or SQL Server to prevent cross-tenant leakage?
46. How do you design idempotency using relational tables (unique constraints/keys) to avoid duplicate processing on retries?
47. How do you ensure referential integrity when a REST API updates multiple related tables?
48. What security practices did you implement for HIPAA / FedRAMP-style compliance in microservices platforms?
49. What is the difference between API Gateway and Service Mesh?
50. What is Dispatcher Servlet vs Eureka / service registry as a centralized node?
51. How would you distribute Order, Shipment, and Billing in a microservices architecture?
52. There are User, Inventory, and Checkout services. Checkout is slow and exhausts User service resources, so Inventory calls fail. How do you handle this so User resources are not exhausted by one downstream?
53. A for-loop keeps calling Microservice-A until it starts denying service. How do you handle that?
54. You received 1 million records from a database query. How do you process this data efficiently?
55. How do you design a database that can handle high concurrency?
56. How would you design the data model for a platform? What factors would you consider?
57. Explain what patterns you would use when an event is generated by one service and multiple services are waiting for that event.
58. Design a pattern to track a website hit counter.
59. What is CAP theorem?
60. What is load balancing in microservices, and how does it work?
61. How do you implement load balancing in AWS? What is the difference between ALB and NLB?
62. How do you trace an error in a multiple-service environment where one service calls another?
63. What are synchronous and asynchronous microservices? How is asynchronous communication done?

---

## 6. Apache Kafka and Messaging

1. Explain Kafka architecture and main components.
2. How do you guarantee ordering? What are the trade-offs?
3. Can a single consumer read from multiple partitions simultaneously?
4. What happens when a Kafka broker goes down while services are running?
5. What happens when consumer lag increases? How do you reduce it?
6. Walk through consumer rebalance. How do you prevent rebalance storms?
7. At-least-once vs at-most-once vs exactly-once — how do you configure each?
8. What is a poison pill, and how do you design a DLT?
9. How do you handle Kafka schema evolution without breaking consumers?
10. How do you prevent duplicate processing during consumer rebalancing?
11. Idempotent producer vs transactional producer — when do you need both?
12. How do you choose partition count and keys?
13. How do you handle hot partitions / data skew?
14. Kafka vs RabbitMQ vs Azure Service Bus vs SQS — how do you choose?
15. How do you tune producer `batch.size`, `linger.ms`, and compression?
16. How do you implement retry topics vs blocking retries?
17. How do you test Kafka consumers (embedded Kafka, Testcontainers, contract tests)?
18. What is consumer group and offset management? Auto-commit vs manual commit?
19. How do you process events with virtual threads vs reactive Kafka?
20. How would you design strict chronological processing across entities?
21. Kafka delivers a message twice. How is your consumer safe?
22. How do you test transactional outbox correctness (crash between DB commit and publish)?
23. How do you ensure exactly-once effects using relational storage plus outbox consistency?
24. What is the difference between Kafka topics and partitions?
25. Kafka sends a message to a service. What happens if the service is down?
26. How do you make message delivery fault-tolerant with RabbitMQ / Kafka?
27. What changes did you observe when you moved from RabbitMQ to Azure Service Bus?

---

## 7. SQL and Database

1. How do you resolve database performance issues?
2. What is indexing, how does it help, and what are the downsides?
3. Queries are slow even without JOINs or N+1 — what else do you check?
4. Difference between WHERE and HAVING?
5. What is `PARTITION BY`, and how does it differ from GROUP BY?
6. Write a query to find employees whose salary is greater than the average salary of their department.
7. Increase salary of all employees in a department by 10% and list new salaries (multi-table).
8. ACID properties — how do you ensure transactional integrity?
9. Database normalization vs denormalization — when do you denormalize?
10. Types of relationships: one-to-one, one-to-many, many-to-many?
11. Types of indexes, and how do you decide which to use?
12. How do you handle data migrations and schema changes with zero downtime (expand/contract)?
13. How do you ensure data consistency in a distributed / microservices database landscape?
14. How do you handle backups and disaster recovery (RPO/RTO)?
15. How do you optimize queries (execution plan, indexes, parameterization)?
16. Clustered vs non-clustered indexes?
17. How do you handle connection pooling and why oversized pools hurt?
18. How do you prevent inconsistent data when multiple users update the same record?
19. Difference between pessimistic DB locks and application-level locks?
20. How do you shard or partition data, and how do you choose a shard key?
21. SQL vs NoSQL — how do you actually decide?
22. How do you secure database connections (TLS, least-privilege, secrets)?
23. How do you handle PII, encryption at rest, and compliance (GDPR)?
24. What is query result caching, and when does it go stale?
25. What is the difference between UNION and UNION ALL?
26. What is the difference between LEFT JOIN and RIGHT JOIN?
27. When do you use LEFT JOIN?
28. How do you find records in one table that have no relationship with another?
29. How do you handle NULL values and conditional mapping in SQL?
30. How do you map values like A to Apple, B to Banana in SQL?
31. How do you remove duplicates in SQL?
32. How have you designed relational schemas for auditing (who/what/when) without bloating tables or harming query performance?
33. How do you validate data integrity across tables and row counts during a large migration?
34. Describe a time you optimized slow queries: indexes, query rewrites, and explain-plan tactics.
35. What is the difference between INNER JOIN and SELF JOIN?
36. What are the different types of joins? Explain INNER, LEFT, and RIGHT JOIN with real examples.
37. How do you find the 2nd / 3rd highest salary (optionally per department)?
38. SQL: max salary of an employee from two tables.
39. Suppose a column has duplicate values. Retrieve the values that have duplicates.
40. What are database triggers?
41. What is a database view?
42. What is the difference between DML and DDL?
43. What are Primary Key vs Unique Key?
44. How do you manage NULL in the DB and in queries?
45. How can too many indexes on a table reduce query performance?
46. If you want to reduce the number of transactions on the database, how do you do that?
47. List all departments and the number of employees in each department.
48. List employees who earn less than their managers.
49. Query to print employee name and its department name. What is the output if `deptId` is NULL?
50. SQL query to find employee name with its count in a department.
51. Given `order(id)` and `customer(id, order_id, country)`, select the top 5 countries with the highest orders.
52. Given Student, Class, and Teacher tables, find `teacher_name` for student Ravi.
53. Given USER and CITY tables (including NULL `city_id`), what is the result of INNER JOIN vs LEFT JOIN?
54. What is MongoDB? What are the benefits of MongoDB over SQL?
55. How do you scale a database in AWS RDS?
56. What is JDBC?

---

## 8. Programming / Coding Problems

1. Bike with three gears (5 km, 10 km, 15 km) — how far can it travel? Write a program.
2. Find the nearest palindrome number (130 → 131, 125 → 121).
3. Reverse a string using Java Streams.
4. Count frequency of each employee name from a list of employees.
5. Frequency of every word in input: `Java Spring Java Kafka Kafka Kafka`.
6. Take a name as String and find occurrence of each character using Streams.
7. Check whether a number is a palindrome using `Predicate`.
8. Count vowels in a lowercase English string.
9. From `["One", "2wo", "3hree", "Four", "5ive", "Six"]`, select strings starting with a digit; also produce a map of each such string to its count.
10. Given integers, find all pairs whose sum also exists in the list. Example `{1, 2, 6, 10, 5, 15, 8}` → `{{10, 5}, {2, 6}}`.
11. Given `{1, 1, 1, 2, 33, 4, 4, 4, 4}`, find the two most frequent numbers with counts `{4:4, 1:3}`.
12. Find last repeated and non-repeated characters in `"Good Evening"`.
13. First non-repeating character in `"Application"`.
14. Stably rearrange an array: negatives, then zeros, then positives, preserving relative order. Input `[1, 0, -6, 7, 0, -1, 3, 0, -3]`.
15. Find the topper among students using name, marks, and roll number.
16. Write a Stream API program to solve a grouping/filtering problem (interviewer-given list).
17. Implement LRU cache.
18. Find duplicates in an array in O(n).
19. Two-sum / k-sum variants.
20. Merge overlapping intervals.
21. Producer-consumer with `BlockingQueue` or virtual threads.
22. Rate limiter (token bucket / sliding window) in Java.
23. Detect cycle in a linked list; reverse a linked list.
24. Valid parentheses; longest substring without repeating characters.
25. Level-order traversal of a binary tree; lowest common ancestor.
26. Implement `CompletableFuture` pipeline that calls 3 APIs in parallel and aggregates.
27. Deduplicate a stream of Kafka-like events by key within a time window.
28. Custom `ThreadPoolExecutor` rejection-handler scenario.
29. Parse nested JSON / flatten a map with dotted keys.
30. Implement retry with exponential backoff and jitter (no library).
31. Write SQL + Java together: paginated search with filters and sorting.
32. Design an in-memory pub/sub.
33. Count word frequency in a large file that does not fit in memory.
34. Implement a thread-safe singleton lazy init.
35. Group employees by department and find max salary using Streams.
36. How do you find duplicate strings in a list?
37. Write a program to check whether a string is a palindrome.
38. Solve Combination Sum II using recursion.
39. Using Java Streams: remove odd numbers, multiply each remaining number by a constant, and return the sum.
40. Find the missing integer in a consecutive array.
41. Move all zeroes to the end of an array.
42. Check whether two strings are anagrams.
43. Find the longest common prefix among strings.
44. Find the Longest Increasing Subsequence.
45. Best Time to Buy and Sell Stock.
46. Explain and implement Dijkstra’s Algorithm.
47. Solve the Coin Change problem for minimum coins.
48. Solve the Reverse-Add Palindrome problem.
49. Find the longest substring without repeating characters in Java.
50. How would you build a rate limiter shared by 10 instances?
51. Group servers that share the same value from a `HashMap`.
52. Implement a stack with its operations.
53. Given a string, remove all duplicate characters.
54. Count words in a string such as `" hello my name is abc "`.
55. Truncate a string after the first repeated character (example `"absdwsebsds"` → `"absdwse"`).
56. Given a paragraph, find the most occurred word and its count.
57. Given a list of strings, return those that start with a vowel, uppercased, sorted by length.
58. Create a map where the key is word length and the value is the list of strings of that length.
59. Check whether a string can be a valid palindrome by removing at most one character.
60. Check if a number is a palindrome without converting it to a string.
61. Maximum subarray sum / Kadane (example: `[-2, 1, -3, 4, -1, 2, 1, -5, 4]` or a longer array summing to 19).
62. Merge two sorted arrays into one sorted array in O(n) (with and without `java.util`).
63. Smallest missing positive integer: `[1,2,0]` → 3; `[3,4,-1,1]` → 2; `[7,8,9,11,12]` → 1.
64. From `ArrayList` 1 to 10, check if a pair sums to 18 and give indexes.
65. Starting and ending index of a target in a sorted array: `[1,2,5,5,5,6,7]`, target 5 → 2 and 4.
66. Next greater element: `[1, 3, 2, 4]` → `[3, 4, 4, -1]`.
67. Find 2nd max from an array.
68. Find max profit from prices `{1,3,2,8,3,2,1}` (explain complexity).
69. Repeatedly sum digits until a single digit (38 → 2, 9999 → 9).
70. Print prime numbers / check a prime.
71. Sort a stack using another stack.
72. Compare two `Person` objects using `AgeComparator`. Sort `Person` by age.
73. From two lists (orders and users), generate `Map<String, UserOrders>` with userId, totalOrders, totalAmount; write a Mockito test as well.
74. Java program for an `Employee` class: average salary based on departments.
75. `String a = "Hello"` and `b = "Java"` — print last two chars combined as `"valo"`.
76. Reverse each word: input `"hello how are you?"` → `"olleh woh era ?uoy"` without using loop or stream.
77. Given `"I love Java and I love coding"`, print total characters, occurrence of each character, and occurrence of each word.
78. Print odd and even numbers synchronously using two threads up to 100.
79. Write a program to print 1 to 5 using 3 threads with a delay of 1 second.
80. Time complexity of `for (int i = 0; i < n; i = i * 3)`.
81. Make a singly linked list behave like a Stack.

---

## 9. Angular (including Angular 21)

1. How do you make HTTP requests with `HttpClient` (GET/POST/PUT/DELETE)?
2. What is `ChangeDetectionStrategy.OnPush`, and how does it differ from default?
3. Standalone components vs NgModules — what is the current default, and why?
4. Signals vs RxJS — when do you use each?
5. What are `computed`, `linkedSignal`, and the Resource API?
6. New control flow (`@if`, `@for`, `@switch`) vs `*ngIf` / `*ngFor`?
7. What are deferrable views (`@defer`), and when do you use them?
8. Zoneless change detection — what problem does it solve, and what do you change in the app?
9. Incremental hydration / SSR with Angular — how does it work?
10. How do you share state: Signals, NgRx, component services?
11. How do you implement interceptors for JWT, correlation IDs, and error handling?
12. Lazy loading routes and preloading strategies?
13. How do you guard routes (`CanActivate`, `CanMatch`)?
14. Reactive forms vs template-driven forms — when each?
15. How do you unsubscribe / avoid memory leaks (takeUntilDestroyed, async pipe, DestroyRef)?
16. How do you optimize bundle size (esbuild, budgets, lazy routes, CDK vs Material)?
17. How do you handle environment config for Angular + Spring Boot across Azure/AWS?
18. How do you implement role-based UI hiding vs real authorization on the API?
19. How do you test components, services, and HTTP with TestBed / Jest?
20. How do you handle CORS with a Spring Boot API?
21. TrackBy in `@for` — why does it matter?
22. How do you implement infinite scroll / virtual scroll for large tables?
23. How do you upload files from Angular to Spring Boot (progress, multipart)?
24. How do you secure tokens in the browser (memory vs cookie vs localStorage)?
25. How do you design a micro-frontend vs a modular Angular workspace?
26. Difference between `providedIn: 'root'` and component-level providers?
27. How do you migrate an older Angular app to the latest (standalone, signals, control flow)?
28. How do you ensure accessibility (a11y) and keyboard navigation?
29. How do you handle real-time updates (SSE, WebSocket, polling) in Angular?
30. Best practices for intuitive navigation and mobile-first layout?
31. What is routing in Angular?
32. Difference between reactive forms and template-driven forms?
33. How do you design client-side observability in Angular (logging, error reporting, metrics) for production issues?
34. How would you design frontend validation for REST workflows with OAuth2/JWT so users cannot submit invalid states across retries?
35. How would you design an Angular 21 frontend for tenant-based workflows using idempotent REST APIs and OpenAPI contracts?
36. What strategies do you use in Angular to optimize performance for large, dynamic datasets and frequent UI updates?
37. How would you design a reusable UI framework for audit views and rule-execution results across modules?
38. How do you structure Angular services and modules for maintainability when microservices drive dashboards and reports?
39. How do you implement frontend performance monitoring for Angular (similar to Datadog/Grafana patterns)?
40. How do you align Angular UI behavior with Spring Boot REST contracts, especially validation and error mapping?
41. Describe a time you needed complex TypeScript data mapping for UI; how did you ensure correctness and test coverage?
42. How would you apply idempotent thinking on the frontend to prevent duplicate actions (double-click, retries)?
43. What is change detection in Angular? What is the difference between the constructor and `ngOnInit`?
44. What are the lifecycle methods / hooks of a component? When is `ngOnDestroy` called?
45. How do components communicate? What is `@Input` and `@Output`?
46. There are two independent components, Filter and Book, under App. How do they communicate so Book filters based on Filter?
47. Three dropdowns: the third should change only when the first two are set. How do you implement this?
48. Write Angular code for increment and decrement with two buttons; decrement should disable when the value is 0.
49. What is the difference between a component and a service? A component and a directive?
50. What are Angular directives? How do you create a custom directive?
51. What is a pipe in Angular? What is a decorator?
52. What is an Observable vs a Promise?
53. What is Angular bootstrapping? What is RxJS? What is Angular Material?
54. What is one-way vs two-way binding?
55. What is the difference between Angular and AngularJS? What is `$rootScope`?
56. What is `==` vs `===`?
57. How do you handle state in an Angular application that calls multiple microservices?
58. How do you improve the performance of an Angular page that is taking time to load?
59. How do you handle errors in JavaScript?
60. What is a closure in JavaScript?
61. Arrow functions in TypeScript vs normal functions.
62. How is Redux used with TypeScript?
63. What is debouncing in JavaScript?
64. How do you write an AJAX call from Angular / JavaScript?
65. Button click and component value change — how do you code it?
66. Have you performed an Angular migration? What did you take care of? What Angular 21 features have you adopted?

---

## 10. Azure

1. How have you used Azure DevOps Pipelines for CI/CD?
2. App Service vs AKS vs Azure Functions — how do you choose?
3. How do you deploy a Spring Boot app to AKS with zero downtime?
4. How do you manage secrets with Azure Key Vault and Managed Identity (no passwords in config)?
5. Azure Service Bus vs Event Hubs vs Kafka on HDInsight/Confluent — when each?
6. How do you use Azure Blob Storage for large uploads and SAS tokens?
7. How do you configure Azure Front Door / Application Gateway / API Management?
8. How do you implement private endpoints and VNet integration for a microservice?
9. How do you monitor Spring Boot on Azure (App Insights, Log Analytics, OpenTelemetry)?
10. How do you size Azure Database for PostgreSQL/MySQL vs Azure SQL vs Cosmos DB?
11. How do you implement Azure AD / Entra ID OAuth2 for Angular + Spring Boot?
12. How do you handle config with Azure App Configuration and feature flags?
13. How do you set up blue-green or canary on AKS / App Service slots?
14. How do you implement disaster recovery across Azure regions?
15. How do you use Azure Cache for Redis in a multi-instance Spring Boot app?
16. What IAM mistakes have you seen with overly broad roles?
17. How do you scan containers and dependencies in Azure pipelines?
18. How do you cost-optimize AKS (spot nodes, HPA, rightsizing)?
19. What is the difference between Kubernetes ConfigMaps (for example in AKS) or Azure App Configuration versus Azure Key Vault?
20. What is Azure Service Bus, and how do you handle a dead-letter queue?

---

## 11. AWS

1. How have you used AWS for full-stack deployments (ECS/EKS, EC2, Elastic Beanstalk, Lambda)?
2. How do you deploy Spring Boot on ECS Fargate vs EKS?
3. SQS vs SNS vs Kinesis vs MSK — how do you choose vs Kafka?
4. How do you use S3 for documents, lifecycle rules, and CloudFront?
5. How do you implement IAM least privilege for a microservice?
6. Secrets Manager vs Parameter Store vs environment variables?
7. How do you use RDS (Multi-AZ, read replicas) with HikariCP?
8. When would you pick DynamoDB over RDS?
9. How do you design an ALB + target group + autoscaling setup?
10. How do you observe the system (CloudWatch, X-Ray, OpenTelemetry)?
11. How do you run Spring Boot on Lambda (snapstart / native image) and when is it a bad idea?
12. How do you implement S3 multipart upload for large files from Angular?
13. How do you secure APIs with Cognito or a custom JWT issuer + API Gateway?
14. How do you do multi-account / multi-environment promotion?
15. How do you handle AWS cost spikes after a traffic surge?
16. VPC, subnets, NAT, security groups — draw a typical microservice network.
17. How do you implement backup and PITR for RDS?
18. How do you use ElastiCache (Redis) and avoid cache stampedes?
19. What AWS permissions are needed before working with an S3 bucket?
20. How can serverless be achieved using AWS Lambda or EC2?

---

## 12. Docker, Kubernetes, DevOps, CI/CD

1. Which CI/CD tool have you used, and how does your pipeline work?
2. Do you have DevOps experience? Which tools?
3. Advantages of Helm charts in Kubernetes CI/CD?
4. How are canaries used in a deployment process?
5. Liveness vs readiness vs startup probes — what happens on failure?
6. How do you ensure zero-downtime rolling updates with Spring Boot (preStop, graceful shutdown, probes)?
7. Why is running Flyway on every pod startup an anti-pattern, and what do you do instead?
8. How do you build a small, secure container image for Java 21 (distroless, jlink, layered jars)?
9. How does HPA work, and which metrics do you scale on?
10. ConfigMaps vs Secrets vs external secret stores?
11. How do you debug a CrashLoopBackOff?
12. Resource requests vs limits — what happens with CPU throttling?
13. How do you implement network policies / service mesh (Istio/Linkerd) if asked?
14. Git merge vs rebase — when do you mandate each?
15. How do you resolve merge conflicts without breaking production?
16. Production-ready branching strategy and hotfix lane?
17. How do you keep feature branches short-lived?
18. What do you look for in a code review as a senior engineer?
19. How do you use feature flags for safer releases?
20. Blue-green vs rolling vs canary vs recreate?
21. How do StatefulSets in Kubernetes differ from Deployments?
22. What is the difference between Docker volumes and bind mounts?
23. How do you implement rolling updates in Kubernetes?
24. What is versioning in Git (for example 1.0.1)?
25. How do you revert a faulty commit in Git?
26. What are the Scrum / sprint ceremonies?

---

## 13. Caching, Performance, and Production Troubleshooting

1. API latency suddenly increases after deployment. What do you check first?
2. Database connection pool is exhausted. What could be the reason?
3. API works locally but is slow in production. How do you debug it?
4. Memory usage keeps increasing until crash. How do you find the root cause?
5. One downstream service is slow and affects the entire API. How do you isolate impact?
6. Cache improves performance but serves stale data. How do you fix it?
7. Scheduled job runs multiple times after scaling instances. Why?
8. Application is healthy, but users still get timeouts. What do you investigate?
9. API is slow even though the DB query is fast. Where else is the bottleneck?
10. Logs exist across services, but tracing one request is hard. What do you implement?
11. Traffic increases 10x. What do you check before adding servers?
12. Works in staging, fails in production. What differences do you compare?
13. A service crashes only under heavy load. How do you find the root cause?
14. App is fine in QA, page freezes in production. How do you troubleshoot?
15. Three pillars of observability — how do you use them for a 504 in Kubernetes?
16. How do you monitor health in production? Tools and metrics?
17. How do you optimize a full-stack application (DB, cache, payload, N+1, bundle, CDN)?
18. How do you handle ThreadLocal memory leaks?
19. How do you prevent GC pause-induced latency?
20. How would you design disaster recovery for near-zero data loss?
21. How do you find the reason behind a server crash?
22. How do you check server memory usage?
23. How do you debug high CPU or memory issues in a JVM?
24. How do you capture Heap Dumps and Thread Dumps?
25. Different ways of non-blocking processing of files.
26. How do you keep services resilient under downstream slowness?
27. How do you design for high concurrency at the database and API layers?

---

## 14. Security

1. How do you protect a web app from XSS? Example?
2. How do you prevent sensitive information exposure?
3. What is CSRF, and how do you prevent it?
4. Security measures when designing authentication?
5. Role of encryption — example in your stack?
6. Security considerations when developing APIs?
7. How do you mitigate file-upload vulnerabilities?
8. How do you protect credentials (hashing, MFA, rotation)?
9. Secure handling and storage of sensitive data?
10. How do you prevent clickjacking?
11. Security best practices for cloud infrastructure?
12. Common client-side JavaScript vulnerabilities and prevention?
13. Secure transmission between client and server?
14. How do you protect session data?
15. How do you keep up with vulnerabilities and dependency CVEs?
16. How do you handle security incidents?
17. Common REST API vulnerabilities and prevention?
18. Security of user-uploaded files?
19. Third-party library risk — how do you manage it?
20. Explain XSS, CSRF, CORS, and SQL injection.
21. Difference between encryption, decryption, encoding, and hashing?
22. Why is encoding required, and where have you used it?
23. How do you implement CORS correctly with Angular + Spring Boot (credentials, no `*`)?
24. How do you rotate JWT keys / use JWKS?
25. How do you implement method-level security (`@PreAuthorize`)?
26. How do you avoid IDOR / insecure direct object references?
27. How do you implement secrets scanning in CI?
28. What is Zero Trust for service-to-service calls?
29. How does JWT authentication work? How is a token validated on the server side?
30. What is the difference between Access Token and Refresh Token?
31. What happens when a user tries to log in, in terms of authentication?
32. How have you designed RBAC in your project? What annotation handles RBAC?
33. Create a DB design that handles user-based role mapping.
34. What is OAuth2, and how do you write the configuration?
35. What is the difference between an API key and a JWT token?
36. What is the difference between stateful and stateless authentication, and what are the benefits?

---

## 15. Testing and Quality

1. How do you structure unit vs integration vs contract vs e2e tests?
2. How do you test a service that talks to Kafka and a DB?
3. How do you mock downstream APIs (WireMock, Testcontainers)?
4. What is Testcontainers, and where does it beat `@SpringBootTest` with H2?
5. How do you keep tests deterministic under concurrency?
6. How do you measure coverage vs mutation testing — what actually matters?
7. How do you test Angular OnPush / signal-based components?
8. How do you test security rules (unauthorized, forbidden, CSRF)?
9. How do you test migrations?
10. What is your definition of clean code, and what do you enforce in PRs?
11. Time vs space complexity trade-offs in high-throughput services?
12. How do you handle edge cases and defensive coding?
13. Process before writing a single line of code for an ambiguous problem?
14. How do you verify a method is called twice in Mockito?
15. In which situations do you use PowerMock?
16. How do you test transactional outbox / exactly-once processing under crash and retry?
17. When you remediate SonarQube or Snyk findings, what is your step-by-step dependency update and verification process?
18. How do you prevent flaky tests in CI for REST APIs and rule-heavy services?
19. How do you maintain high code coverage without writing brittle tests?
20. How do you write unit tests? What annotations have you used, and what do you focus on?
21. How do you write Mockito tests? Which annotations are used?
22. Can you mark static methods in JUnit? Can you mark private methods in JUnit?
23. What is integration testing, regression testing, and sanity testing?

---

## 16. System Design (Senior)

1. Design a URL shortener.
2. Design a payment processing system (idempotency, exactly-once effects).
3. Design a notification system (email/SMS/push) with Kafka.
4. Design real-time chat.
5. Design e-commerce order + inventory under concurrent stock.
6. Design a file storage system (Dropbox-like) with 10 GB uploads.
7. Design a rate-limited public API on Azure/AWS.
8. Design search with pagination that stays consistent.
9. Design an audit log / event sourcing pipeline.
10. Design multi-tenant SaaS isolation (DB-per-tenant vs shared).
11. How do you gather requirements and NFRs before drawing boxes?
12. Back-of-the-envelope capacity estimation?
13. SQL vs NoSQL for a given component?
14. What to cache and where?
15. When to introduce sharding vs when it is premature?
16. HA vs DR — RTO and RPO?
17. Horizontal vs vertical scaling; why services must be stateless?
18. Session management when you scale out?
19. Layer 4 vs Layer 7 load balancing?
20. Failure scenarios you raise proactively in a design interview?
21. Explain the design of one of your recent projects.
22. How would you design a Fraud Detection System for transactions?
23. Design a database for a Ride-Sharing application.
24. Design a Data Warehouse for an online retailer.
25. Design a News Aggregator.

---

## 17. Project, Architecture, and Senior Role

1. Walk through your current product, architecture, key features, and your role.
2. What features did you own end to end?
3. What is the technology stack, and why were those choices made?
4. Is the work greenfield, brownfield, or maintenance — and how does that change your approach?
5. Who provides requirements, and what is the path from requirement to production?
6. Team size and how responsibilities are split?
7. Most critical challenge you faced, and how you resolved it?
8. What improvements or initiatives did you introduce?
9. How do you document work so others can maintain it?
10. How are KPIs measured for an engineer / SSE?
11. What do you focus on during code review?
12. Roles and responsibilities of a Senior Software Engineer?
13. How do you implement a dynamic choice/selection feature in the app you described?
14. Marker interfaces or patterns you used in the project?
15. How do you collaborate with QA, DevOps, and product?
16. How do you onboard a new developer on your service?
17. A production incident you led — timeline, RCA, and prevention?
18. How do you use AI tools in day-to-day engineering, and how do you verify output?
19. How do you keep skills current (Java 21, Angular, cloud)?
20. How would you design intuitive navigation and mobile-first UX on your project?
21. How do you handle third-party library customization without forking blindly?
22. If two Spring beans conflict from libraries, how did you resolve it in a real project?
23. What observability did you add that was not there before?
24. How do you estimate stories and call out risk early?
25. How do you push back on an impossible deadline?
26. Tell me about an incident you led. What changed afterwards?
27. What do you look at first in a junior's pull request?
28. Which of your design decisions turned out wrong? What did you learn?
29. How do you stay organized and manage time across multiple tasks or projects?
30. Tell me about a time dependency upgrades improved error rate or latency; what changed in the build or libraries?
31. With many CVE remediations across many microservices, how do you prioritize and verify no regressions?
32. How did you design secret-key reveal and masking features, and what authorization checks ensured only permitted users could unmask data?
33. Explain the development and design process in your project.
34. How do you monitor logs?
35. Which monitoring tools have you used, and how did you use them to monitor health and performance?
36. How do you approach a production issue?
37. If the system hangs, how can you identify the cause?
38. A scheduler must run every 6 hours. There are 5 pods. How do you ensure only one pod executes it at a time?

---

## 18. HR / Behavioral / Managerial

1. Tell me about yourself.
2. Why should we hire you?
3. Why do you want to work here?
4. What are your strengths?
5. What is your greatest weakness?
6. Why are you leaving your current job?
7. Where do you see yourself in five years?
8. Tell me about a challenge you faced and how you handled it.
9. What motivates you?
10. Do you have any questions for me?
11. What are your roles and responsibilities today?
12. Walk through your family background only if asked — keep it professional and brief.
13. Reason for changing jobs?
14. Previous company history without criticizing anyone?
15. How would you describe the work culture you prefer?
16. Areas of interest (technical and otherwise)?
17. How do you manage workload and work-life balance?
18. How would you rate yourself on technical skills, communication, and time management?
19. Current CTC, expected CTC, and notice period?
20. Can you join earlier? How would you handle handover?
21. What will you do if you get a counteroffer?
22. Do you have other offers?
23. Are salary expectations negotiable?
24. Are you willing to relocate or work hybrid/office as required?
25. You've changed jobs — why, and why will you stay now?
26. How long do you plan to stay?
27. How do you explain any career gap?
28. Tell me about a time you disagreed with your manager.
29. Biggest professional failure and what you learned?
30. What would your current manager say about you?
31. Have you coached or managed an underperforming teammate?
32. How do you handle restructuring or new leadership?
33. Tell me about a time you handled an unhappy stakeholder.
34. How do you work under tight deadlines?
35. How do you handle feedback?
36. Toughest decision you made at work?
37. What would you do if a colleague broke policy?
38. How do you work in hybrid/remote teams?
39. How do you use AI at work responsibly?
40. How do you keep skills up to date?
41. Office vs remote vs hybrid preference?
42. What does work-life balance mean to you?
43. Something you learned on your own recently?
44. What would you do in the first 90 days?
45. On a scale of 1 to 10, how would you rate yourself?
46. Proudest achievement?
47. What frustrates you at work?
48. If money were no object, would you still work?
49. Any career regrets?
50. What do colleagues say about you?
51. Why should we not hire you?
52. Are you a team player? Example?
53. Hard work vs smart work?
54. Tell me about a time you improved a process.
55. Tell me about a time you delivered under ambiguity.
56. Tell me about a time you had to learn a new stack quickly (example: Angular upgrade, Kafka, cloud).
57. Tell me about a production outage you helped resolve.
58. How do you handle conflict within the team?
59. How do you prioritize when everything is P1?
60. Questions to ask them: first 90 days, team challenges, performance reviews, learning support, next steps.

---

## 19. Full-Stack Cross-Cutting (added for 8 YOE)

1. How do you split work between Angular and Spring Boot so contracts stay stable?
2. How do you version BFF vs public API vs internal events?
3. How do you keep frontend and backend error models consistent?
4. How do you implement end-to-end idempotency from Angular double-submit to Kafka consumer?
5. How do you do contract testing (Pact/OpenAPI) between UI and API?
6. How do you handle feature flags that affect both UI and API?
7. How do you design optimistic UI updates with rollback on API failure?
8. How do you prevent over-fetching from Angular (pagination, projections, GraphQL if used)?
9. How do you implement distributed tracing from browser (W3C traceparent) through gateway, services, and Kafka?
10. How do you manage CORS, cookies, CSRF, and SameSite in a SPA + API architecture?
11. How do you structure a mono-repo vs multi-repo for Java + Angular?
12. How do you run local full stack (Docker Compose: API, Kafka, Redis, DB, UI)?
13. How do you enforce API backward compatibility while shipping UI weekly?
14. How do you approach accessibility, i18n, and date/time/timezone across stack?
15. How would you introduce Java 21 virtual threads into an existing Tomcat Spring Boot service without breaking JDBC/pinning?
16. How would you migrate a blocking RestTemplate fleet to WebClient or JDK HttpClient?
17. How do you decide Redis vs DB vs Kafka Streams for a read model?
18. How do you implement multi-cloud awareness (Azure primary, AWS DR) without leaking cloud SDKs everywhere?
19. How do you apply 12-factor config in Spring Boot 3 + Angular environments?
20. What would you automate first in a team with flaky prod releases?
21. How do you design your dependency strategy to support both AWS and Azure without duplicating library configuration?
22. How do you design schema evolution for MS SQL and PostgreSQL so Kafka workflows and APIs do not break?
23. How do you design HIPAA/CUI-friendly auditing with encryption, masking, and acceptable query performance together?

---