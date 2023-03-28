# @Annotations
- @RestController ប្រើសម្រាប់ កំណត់ថា class មួយណាដែលជា controller class ឬកំណត់ទីតាំងដើម្បី ស្គាល់ controller
- @RequestMapping("api/") សម្រាប់ Request rout ទៅ endpoint ណាមួយ
- @MappedSuperclass ប្រើសម្រាប់ចែកfields មានន័យថា យើងមាន class មួយជាមេ ឬentity មួយជាមេ សម្រាប់ចែក fields ដែលមាននៅក្នុង Base Entity ទៅកាន់ Entity កូនៗ
- @Table(name = “ ”) សម្រាប់ដាក់ឈ្មោះទៅឲ្យ Entity
- @ManyToMany សម្រាប់ ចងrelationship, FetchType.LAZY សម្រាប់ទាញ entity មកហើយយើងចង់ទាញ row ដែលនៅក្នុង entity នោះមកអត់, មានន័យថា បើគេអត់ហៅ FetchType.LAZY មកប្រើទេ គឺអត់ទាញ data មកទេ
- @Basic សម្រាប់ default column នៅក្នុង Entity db។ Ex: column id មានdata type ជាlong អញ្ចឹង default វាគឺ 64, data type ជា String អញ្ចឹង default វាគឺ 255 តួអក្សរ
- @Id សម្រាប់កំណត់ថា Column ហ្នឹងជា id
- @GeneratedValue សម្រាប់កំណត់ការ Generate Type ID ទៅជា auto ID(auto លេខ ឬលេខអត់តាមលំដាប់) ឬទៅជា ID IDENTITY(រត់តាមលំដាប់លេខ)
- @Column សម្រាប់កំណត់ attribute ឬcolumn នៅក្នុង Database ថាអាច null បានអត់? កំណត់ length បានប៉ុន្មាន កំណត់ unique ថា column មួយហ្នឹងជា optional ឬក៏ unique
- @NoRepositoryBean គឺមិនឲ្យបង្កើត Bean ថ្មី
- @Repository សម្រាប់កំណត់ ថាវាជាប្រភេទ component ដែលធ្វើការទៅលើ repository ។ ហើយត្រូវ Extend ចេញពី JpaRepository មួយទៀតទើបដំណើរការបាន Ex: CategoryRepository: JpaRespository<CategoryEntity, Long> (ចំណាំ <name_entity, type_id ជាអីគេ>) បើ type ជា Long ត្រូវដាក់ Long បើជា String ត្រូវដាក់ String…
- @Transient កុំឲ្យ data របស់ variable or function calculate វា store នៅក្នុង db
- @RestController សម្រាប់កំណត់ថា វាជាប្រភេទ Controller ហើយបង្កើតជា API ទៀត
- @RequestMapping(“/”) សម្រាប់បញ្ជាក់ថា ឲ្យវាស្ថិតនៅ endpoint ណាមួយ
- @GetMapping សម្រាប់ទៅ get ឬចូលទៅ endpoint ណាមួយដែលយើងចង់ get ។ ហើយ @GetMapping យើងអាចដាក់ rout បន្តបានទៀត Ex: @GetMapping(“/get”)
- @Service សម្រាប់កំណត់ថា class interface មួយហ្នឹងជា service
- @Autowired សម្រាប់ inject dependencies យកមកប្រើបា្រស់
- @PostMapping សម្រាប់ បញ្ជួនឬ post ទៅកាន់ endpoint ឬrout ណាមួយ
- @RequestBody សម្រាប់ ស្នើសុំ ឬrequest ទិន្នន័យណាដែលយើង ចង់បង្កើតដើម្បីឲ្យ user អាចបញ្ចូលទិន្នន័យបាន
- @JsonInclude(JsonInclude.Include.NON_NULL) បើសិនជា Field page វា Null ចឹង @JsonInclude អត់ឲ្យ Properties ចេញមកទេ, ទាល់តែវាអត់ null បានឲ្យចេញមក
- @JsonIgnore hide data មិនចង់បង្ហាញ client ឃើញ។ Ex: ដូចជា password, date of birth, etc
- @Transactional ប្រើសម្រាប់ ការធ្វើប្រតិបត្តិការអ្វីមួយ ដោយក្នុងប្រតិបត្តិការនោះមាន Process ២ ឬ ច្រើនជាងនេះ Process ទី១ update table user, និង process ទី២ update table invoice អញ្ចឹង អាពីរ process នេះ បើមួយណា update មិន success ទេ វានិង role back មកវិញទាំងអស់, វាអត់ update មួយ ហើយមួយទៀត អត់ update ទេ និយាយទៅដូចឈ្នាប់ AND ដែរ បើវាពិតត្រូវពិតទាំងអស់។
- @Component Annotation គឺជាមេ ពពួក (@Repository, @Service, @Controller)
- @Controller Annotation
- @Configuration Annotation សម្រាប់ ឲ្យ spring boot ជាអ្នកធ្វើការ configure ជំនួសដោយគ្រាន់តែ ដាក់ annotation មួយនេះ នៅលើ class config
- @Ordered Annotation
- @Lazy Annotation <br>
<details>
<summary>@JsonIgnoreProperties(ignoreUnknown = true)</summary>
<p>
ប្រើសម្រាប់ថាឧទាហរណ៍ពេលយើង object នឹងចូល database ឧបមារថា save ចូលមាន field id, name អីចឹងទៅ ហើយស្រាប់តែលើកក្រោយយើងថែម sex មួយទៀត ចឹងបើយើងប្រើ jsonIgnoreproperties នឹងគឹវាអត់ error អីទេ តែបើអត់ប្រើ វានឹង error ថាវារក field sex ទិន្នន័យចាស់ៗអត់ឃើញ ចឹងវាតម្រូវឲ្យយើងទៅដាក់ field sex នៅគ្រប់ទិន្នន័យចាស់ៗទាំងអស់។ 
</p>
</details>
<details>
<summary>@ComponentScan Annotation</summary> 
<p>
ភាគច្រើន ប្រើនៅកន្លែង config file ដែលយើងចង់ឲ្យវា scan នូវ package ណាមួយ (អាចដាក់ ឈ្មោះជា package ក៏បាន ឬជាឈ្មោះ class ក៏បាន ហើយអាច ប្រើបានជា multiple បានទៀត)
Example in java code:
</p>
</details>
<details>
<summary>@Bean Annotation</summary> 
<p>
សម្រាប់ ដាក់នៅលើ function ណា ដែលយើងចង់ឲ្យវាក្លាយទៅជា bean, Bean មានន័យថា object មួយដែលយើងយកមកប្រកាស់ជា public ដែលនៅក្នុង project ទាំងមូល កន្លែងណាក៏អាច ហៅប្រើវាបានដែរ ហើយវាប្រកាស់ តែម្ដងទេ (Singleton)
</p>
</details>
<details>
<summary>@Qualifier Annotation</summary>
<p>
មានន័យថា នៅពេលមាន ប្រភេទ Bean លើសពីមួយដែល Bean នោះវាជា ប្រភេទដូចគ្នា ឬ Bean តែមួយនៅក្នុង Spring Applicaton Context យើងត្រូវប្រើប្រាស់ qualifier ដើម្បីបញ្ជាក់ ឈ្មោះផ្សេងគ្នា មានន័យថា មាន Bean ពីរ ផ្សេងគ្នា ដែល Bean នោះជាប្រភេទតែមួយ
  <br>Example Code:
  
```java
public class UserService {
    private final UserRepository userRepository;

    public UserService(@Qualifier("userRepositoryImpl1") UserRepository userRepository) {
        this.userRepository = userRepository;
    }
}

```
  </p>
 </details>
