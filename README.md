How to run this simple Java file in Docker.
📝 Step 1: Create a Simple Java Program
Create a file named HelloWorld.java
  public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello from Dockerized Java!");
    }
}
📂 Step 2: Create a Project Folder
Make a directory for your project:
mkdir java-docker-demo
cd java-docker-demo

Place HelloWorld.java inside this folder.

🐳 Step 3: Write a Dockerfile
Create a file named Dockerfile in the same folder
    # Use official OpenJDK image
    FROM eclipse-temurin:17-jdk-alpine
    
    # Set working directory inside container
    WORKDIR /app
    
    # Copy Java source code into container
    COPY HelloWorld.java .
    
    # Compile the Java program
    RUN javac HelloWorld.java
    
    # Run the program
    CMD ["java", "HelloWorld"]
    
⚙️ Step 4: Build the Docker Image
Run this command in the project folder:
  docker build -t java-docker-demo .

▶️ Step 5: Run the Containe
  docker run --rm java-docker-demo
  
    Expected output:
      Hello from Dockerized Java!



🐳 Run a Container from Your Image
- List your images to confirm the name
  docker images

  - Run the image:
    docker run --name my-java-container java-docker-demo

      - --name my-java-container gives your container a readable name.
      - Replace java-docker-demo with your image name.

