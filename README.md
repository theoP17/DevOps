# DevOps
## TD1

## TP1
### Database Basics
#### Why should we run the container with a flag -e to give the environment variables?
Running a container with the -e flag to provide environment variables allows dynamic configuration, enhances security, and supports environment-specific setups without modifying the container image.
### Persist data
#### Why do we need a volume to be attached to our postgres container?
Attaching a volume to a PostgreSQL container is essential for persisting data beyond the container's lifecycle. Without a volume, all data stored in the container is lost when the container is stopped or removed. Volumes enable data durability, allowing databases to retain information between container restarts, updates, and migrations. They also facilitate data backup, recovery, and sharing across multiple containers if needed. Additionally, volumes provide better I/O performance compared to container storage and ensure data consistency and reliability for production-grade applications.
### Backend API
#### Why do we need a multistage build?
A multistage build in Docker optimizes the image by separating build-time and runtime dependencies, resulting in smaller, more efficient final images. This reduces attack surfaces and improves security by excluding unnecessary files and tools. It also enhances build performance by leveraging Docker's layer caching effectively. Multistage builds streamline the CI/CD pipeline, allowing different stages to use various base images and tools suited to their tasks. Ultimately, it simplifies maintenance and ensures that only essential components are included in the production image, leading to more robust and performant deployments.
### HTTP server
#### Why do we need a reverse proxy?
A reverse proxy is essential for distributing client requests across multiple backend servers, enhancing load balancing and scalability. It improves security by hiding the backend servers' details and providing a single entry point for traffic filtering and protection. Reverse proxies can cache content, reducing server load and improving response times. They enable SSL termination, offloading encryption and decryption tasks from backend servers. Additionally, reverse proxies support URL rewriting and can route requests based on specific rules, facilitating complex deployments and improving overall system reliability and performance.
### Link Application
#### Why is docker-compose so important?
Docker Compose is crucial for managing multi-container Docker applications, simplifying their setup and orchestration with a single YAML configuration file. It enables the definition and running of interconnected services, streamlining the development and deployment process. Compose facilitates environment configuration, making it easy to manage variables and dependencies across different stages. It enhances productivity by allowing developers to replicate production environments locally. Additionally, Docker Compose supports scaling services, provides clear service logs, and integrates seamlessly with CI/CD pipelines, ensuring consistent and efficient application deployment and management.
### Publish
#### Why do we put our images into an online repo?
Putting Docker images into an online repository, such as Docker Hub or a private registry, ensures easy accessibility and sharing across teams and environments. It facilitates continuous integration and deployment (CI/CD) by providing a centralized location for versioned images, enabling consistent and reliable deployments. Online repositories enhance collaboration, allowing teams to use and update common images. They provide security features like access control and vulnerability scanning, ensuring safe image distribution. Additionally, using an online repo simplifies image management, backup, and disaster recovery, ensuring availability and scalability of containerized applications.
### Notes
My docker compose never worked and I still did not understand why. However my GitHub is all of my scripts so there might be errors in it that I couldn't resolve.

## TD2

## TP2
### Build and test you application
#### What is it supposed to do?
The command mvn clean verify in Maven performs a comprehensive build process for Java projects. It starts by cleaning up previous build artifacts (clean), ensuring a fresh build environment. Then, it proceeds to compile source code, execute defined tests (verify), and package the application. The verify phase validates the project against quality metrics and dependencies, ensuring consistency and readiness for deployment. This command is crucial in Continuous Integration (CI) pipelines for automating build and test workflows, providing feedback on code quality and ensuring reliable software releases. It leverages Maven's dependency management to fetch required libraries and plugins, maintaining project integrity and facilitating collaborative development across teams.
#### What are testcontainers?
Testcontainers is a library that provides lightweight, disposable instances of databases, Selenium web browsers, or anything else that can run in a Docker container. It is designed to support testing processes by making it easier to set up the necessary infrastructure for running tests.
### First steps into the CD World
#### Secured Variables, why?
Secured variables, such as those stored in GitHub Secrets or similar environments, are crucial for protecting sensitive information like credentials. They prevent accidental exposure in public repositories and unauthorized access by ensuring data confidentiality. Secured variables are encrypted and only accessible to authorized workflows, enhancing overall security posture. This practice aligns with best security practices, mitigating risks of data breaches and unauthorized usage. It enables safe automation of workflows, including CI/CD pipelines, without compromising sensitive information. Secured variables support compliance requirements by safeguarding access to critical resources and maintaining confidentiality in software development and deployment processes.
#### Why did we put needs: build-and-test-backend on this job?
The needs: build-and-test-backend directive in GitHub Actions establishes a dependency where the build-and-push-docker-image job relies on the successful completion of build-and-test-backend. This ensures that Docker image creation and publishing only proceed when the backend code compiles and tests pass without issues. By enforcing this dependency, it prevents the deployment of unverified or unstable code, maintaining the reliability and integrity of the CI/CD pipeline. This approach optimizes resource utilization by avoiding unnecessary image builds in case of failed backend tests, thereby enhancing overall efficiency and enabling faster feedback cycles during software development and deployment.
#### For what purpose do we need to push docker images?
We push Docker images primarily for deploying applications consistently across different environments. By pushing images to repositories like Docker Hub or private registries, we make them accessible for deployment on various infrastructure platforms. This practice supports Continuous Integration/Continuous Deployment (CI/CD) workflows, enabling automated deployments and updates. Docker images encapsulate applications and their dependencies, ensuring consistency in deployment across development, testing, and production environments. Pushing images facilitates version control and rollback capabilities, allowing teams to manage and deploy specific versions of applications as needed. It also supports scalability by enabling quick provisioning of identical application instances. Overall, pushing Docker images promotes efficiency, reproducibility, and reliability in software deployment practices.
### Notes
As in the first TP I couldn't finish this one and my tests did not work. If this readme has not been edited that means that still today I do not know where is my problem.

## TD3

## TP3
### Notes
I couldn't deploy as I was trying to resolve my problems on TP1 and 2 however i have done the work before it and put it in my repository.