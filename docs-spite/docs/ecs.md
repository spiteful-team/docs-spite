## ECS Framework Design

### Core Concepts

#### Entities
- Unique identifiers (64-bit ID + version)
- Containers for components
- No behavior, only data aggregation

#### Components
Four component types based on usage patterns:

1.  **IComponent**: Standard per-entity data
    ```cpp
    struct TransformComponent : IComponent {
        glm::vec3 position{0.0f};
        glm::vec3 rotation{0.0f};
        glm::vec3 scale{1.0f};
    };
    ```

2.  **ISingletonComponent**: Global application state
    ```cpp
    struct VulkanInstanceComponent : ISingletonComponent {
        vk::Instance instance;
    };
    ```

3.  **ISharedComponent**: Immutable shared data
    ```cpp
    struct TextureComponent : ISharedComponent {
        Image texture;
        vk::ImageView imageView;
        vk::Sampler sampler;
    };
    ```

4.  **IEventComponent**: Asynchronous communication
    ```cpp
    struct ModelLoadRequest : IEventComponent {
        Entity entity;
        std::string objFilePath;
        std::string vertShaderPath;
        std::string fragShaderPath;
    };
    ```

#### Systems
- Process components in bulk
- Stateless where possible
- Dependency tracking for activation/deactivation

### Memory Management Strategy

#### Component Storage
- **Structure of Arrays**: Components stored in contiguous arrays
- **Cache-friendly**: Optimal memory layout for system iteration
- **TODO: Aspect**

#### Query Caching
- Cached query results for frequently accessed component combinations
- Automatic invalidation on structural changes
- Minimal overhead for system execution
