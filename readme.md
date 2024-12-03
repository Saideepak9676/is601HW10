### User Management API  

#### Resolved Issues  

**Issue 1: User Fixtures Lacking Necessary Data for Item**  
- The `conftest.py` file contained fixtures that were missing required fields. For example, the `test_user_base_valid` test failed due to the absence of the `nickname` field in the fixture.  
- Updated the `base_user_fixture` to include the `nickname` field and ensure compatibility with all related tests. 
![Link:](https://github.com/Saideepak9676/is601HW10/issues/1)

**Issue 2: User ID Validation**  
- The `test_user_response_valid` pytest failed because the `UserResponse` schema expects a UUID for the `id` field, while the `conftest.py` fixture supplied a non-UUID value.  
- Modified the `id` field in the `conftest.py` fixture to generate valid UUIDs, resolving the validation error and ensuring alignment with the schema requirements.
![Link:](https://github.com/Saideepak9676/is601HW10/issues/3)

**Issue 3: Login Request Validation Error**  
- The `test_login_request_valid` test raised a validation error as the `LoginRequest` model required an `email` field that was missing from the fixture.  
- Updated the `login_request_data` fixture to include the `email` field, ensuring compatibility with the API's requirements and passing tests.  
![Link:](https://github.com/Saideepak9676/is601HW10/issues/3)

**Issue 4: SMTP Connection Failure**  
- Tests were failing due to an inability to connect to the SMTP server, stemming from an incomplete configuration of Mailtrap in the project.  
- Resolved the issue by properly configuring Mailtrap and adding an account to facilitate email-related testing.  
![Link:](https://github.com/Saideepak9676/is601HW10/issues/7)

**Issue 5: Password Validation**  
- Implemented password validation rules to enhance security. The new rules require:  
  - A minimum password length.  
  - At least one special character.  
  - At least one uppercase letter.  
- Added tests to verify these rules and ensure the proper handling of both valid and invalid passwords, including edge cases.  
![Link:](https://github.com/Saideepak9676/is601HW10/issues/9)

**Issue 6: Email Authentication**  
- Improved the email field by enforcing validation rules, including checks for:  
  - A valid "@" symbol.  
  - A proper top-level domain (TLD).  
  - General formatting compliance.  
- Developed comprehensive tests to verify email validation against both common and uncommon edge cases.  
![Link:](https://github.com/Saideepak9676/is601HW10/issues/11)

**Issue 7: Remove Unnecessary User Files**  
- Cleaned up several user-related files by addressing issues such as:  
  - Removing duplicate login routes and functions.  
  - Eliminating unused imports and reorganizing active imports for better readability.  
  - Resolving duplicate field issues in `userListResponse`.  
  - Improving error handling for various edge cases.  
  - Renaming duplicate test cases to avoid conflicts.  
![Link:](https://github.com/Saideepak9676/is601HW10/issues/13)

**Issue 8: Create and Upload the Image to Docker Hub**  
- Updated the repository to build a Docker image of the application.  
- Configured GitHub Actions to build and publish the Docker image to Docker Hub upon successful test completion.  
![Link:](https://github.com/Saideepak9676/is601HW10/issues/15)

---

#### Testing and Coverage  
- Comprehensive testing was performed using `pytest`, achieving **90%+ test coverage**.  
- Added new test cases for:  
  - Email and password validation, including edge cases.  
  - Authentication mechanisms using updated fixtures.  
  - Validation of all API endpoints requiring access tokens.
![image]("C:\Users\gsaid\Downloads\Coverage.jpg")

---

#### Deployment  
- **DockerHub Repository:** Successfully built and deployed the Docker image to Docker Hub.  
- **Improved CI/CD Workflow:** Configured GitHub Actions to automate building, testing, and publishing the image to Docker Hub.
![image]("C:\Users\gsaid\Downloads\Dockerimage.jpg")
---

#### Learning Reflection  

1. **Importance of Testing:**  
   - Running `pytest` after each change allowed me to catch issues early and understand why tests failed. This process made debugging and fixing broken areas of the application efficient and ensured a robust codebase.  

2. **Environment Configuration:**  
   - Properly configuring tools like Mailtrap was critical for running tests successfully. This taught me the importance of setting up external dependencies early in the development process.  

3. **Linter Benefits:**  
   - Having a linter setup provided immediate feedback on code quality, helping me maintain clean and readable code while adhering to best practices.  

4. **Reading Documentation Thoroughly:**  
   - By revisiting project documentation and instructions multiple times, I was able to align my work with project expectations and requirements. This approach helped me gain a deeper understanding of the product lifecycle.  

5. **Schema Validation:**  
   - Debugging schema-related issues (e.g., UUID validation) helped me appreciate the value of aligning test data with API requirements. This improved my ability to identify and resolve data mismatches in other contexts.  

6. **Building a CI/CD Pipeline:**  
   - Configuring GitHub Actions for Docker image deployment was a valuable learning experience. It highlighted the importance of automating builds, tests, and deployments to save time and reduce errors.  

7. **Edge Case Handling:**  
   - Writing extensive tests for email and password validations helped me develop a better understanding of edge case scenarios and how to address them effectively.  

8. **Maintaining Clean Code:**  
   - Cleaning up unused imports, duplicate fields, and redundant files improved code readability and maintainability, reinforcing the importance of regular refactoring.  

9. **Collaboration Through Documentation:**  
   - Writing comprehensive documentation for resolved issues ensures smooth communication with team members and serves as a useful reference for future work.  

Through this project, I gained a well-rounded understanding of building production-ready APIs, incorporating rigorous testing, and deploying applications seamlessly.
