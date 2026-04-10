// Product Entity
@Entity
public class Product {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
    private double price;
        // Getters and Setters
}
// Repository
@Repository
public interface ProductRepository extends JpaRepository<Product, Long> {}
// Controller
@RestController
@RequestMapping("/products")
public class ProductController {
    @Autowired private ProductRepository repository;
      @PostMapping
public Product addProduct(@RequestBody Product product) {
        return repository.save(product);
    }
    @GetMapping("/{id}")
    public Product getProduct(@PathVariable Long id) {
        return repository.findById(id).orElseThrow();
    }
    @GetMapping
    public List<Product> getAllProducts() {
        return repository.findAll();
    }
}
