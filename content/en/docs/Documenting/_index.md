---
title: Documenting
weight: 3
description: The Importance of Good Documentation in Software Development and How to Excel at It.
---

Documentation is a crucial aspect of software development that often receives less attention than coding itself. However, its significance cannot be overstated. Effective documentation not only facilitates collaboration among team members but also ensures the maintainability and longevity of a project.

We'll explore why good documentation matters and provide practical tips on creating it.

## **Why Documentation Matters**

### 1. **Understanding and Onboarding:**

- **New Team Members:** Well-documented code expedites the onboarding process for new team members. Clear documentation provides insights into the codebase's structure, making it easier for developers to understand and contribute to the project.

### 2. **Collaboration:**

- **Team Collaboration:** In a collaborative environment, multiple developers may work on the same project. Proper documentation fosters effective communication by ensuring that everyone understands the purpose, usage, and limitations of the code.

### 3. **Maintainability:**

- **Code Maintenance:** Projects evolve over time, and developers often need to revisit and modify existing code. Good documentation acts as a guide, helping developers maintain and update code without introducing unintended side effects.

### 4. **Troubleshooting and Debugging:**

- **Issue Resolution:** When issues arise, well-documented code aids in troubleshooting. Comprehensive documentation can guide developers in identifying and fixing bugs efficiently.

### 5. **Knowledge Transfer:**

- **Knowledge Preservation:** Documentation is a form of knowledge preservation. It ensures that the rationale behind design decisions, algorithms, and other critical information is retained even as team members come and go.

## **How to Create Good Documentation**

### 1. **Use Meaningful Comments:**

- **Inline Comments:** Embed comments within the code to explain complex sections, highlight important considerations, or provide context. Keep comments concise and focused.

**Examples (Useful comments):**

```Py
# This step is only necessary when working with
# large language models.
# They might ignore some context in the middle,
# so we reorder it to ensure more useful responses.
if len(docs) > 5 and summary:
    docs = self._reorder.transform_documents(documents=docs)
```

```Go
// throw error, if not a slice or map then should not have gotten here
// bad dive tag
panic("dive error! can't dive on a non slice or map")
```

**Examples (Unuseful comments):**

```Py
# Check if length docs > 5
if len(docs) > 5 and summary:
    docs = self._reorder.transform_documents(documents=docs)
```

```Go
// throw error
panic("dive error! can't dive on a non slice or map")
```

### 2. **Write Clear README Files:**

- **Overview:** Include a high-level overview of the project's purpose and functionality.
- **Installation:** Provide clear instructions on how to set up the development environment.
- **Usage:** Detail how to use the software, including code examples or sample inputs.

### 3. **Document Function and Class Purpose:**

- **Function/Method Comments:** Describe the purpose, parameters, and return values of functions/methods.
- **Class Documentation:** Explain the role of each class, its properties, and methods.

### 4. **Include Code Examples:**

- **Usage Examples:** Illustrate how to use key functions or classes with practical examples.
- **Integration Examples:** Provide examples of how the code integrates with other components or modules.

### 5. **Version History:**

- **Changelog:** Maintain a changelog that outlines the changes made in each version of the software. This helps users and developers track the evolution of the project.

### 6. **Consider Your Audience:**

- **User Documentation:** If the code is part of a library or API, create documentation specifically for users, including clear usage instructions and examples.
- **Developer Documentation:** For internal projects, focus on providing details that developers need to understand and contribute to the codebase.

### 7. **Update Documentation Regularly:**

- **Maintenance Routine:** Treat documentation as a living entity. Regularly update it to reflect changes in the code, and ensure that it stays relevant.

## **Don't over-document your code**

Here are some points to keep in mind to avoid excessive documentation or unnecessary comments.

There are situations where explicit documentation or comments become essential. Not every line or routine needs extensive documentation, but strategic comments can provide valuable insights into the codebase.

### **1. Code Clarity:**

- **Self-Explanatory Code:** Aim for code clarity by using meaningful variable/method names and organizing your code logically.
- **Avoid Over-Commenting:** If the code is clear without comments, let it be. Over-commenting can clutter the code and make it harder to read.

### **2. Key Decisions and Considerations:**

- **Document Design Decisions:** If your code makes specific design choices or employs a particular algorithm, a comment can clarify the rationale behind these decisions.
- **Highlight Trade-offs:** If there are trade-offs or compromises in the code, document them to provide context.

### **3. Exceptional Cases:**

- **Special Cases:** Identify and document cases where the code behaves differently due to specific conditions.
- **Known Issues:** If a certain line or block of code is known to have a bug but cannot be fixed immediately, clearly document it to prevent unintentional changes.

```Bazel
js_image_layer(
    name = "layers",
    binary = ":app",
    root = "/app",
    # FIXME: fails with
    # File "any_file.py", line 241, in XXX
    # IsADirectoryError: [Errno 21] Is a directory: '...'
    tags = ["no-remote"],
    visibility = ["//visibility:__pkg__"],
)
```

### **4. Dependencies and Assumptions:**

- **Dependency Information:** Document any external dependencies or assumptions about the environment.
- **Compatibility Notes:** If there are specific requirements or constraints for the code to work, include them in comments.

### **5. Future Considerations:**

- **TODO Comments:** Use "TODO" comments to highlight areas that require further attention or improvement.
  
```Py
#TODO: Add cache
```

- **Deprecated Features:** If a feature is deprecated but hasn't been removed, make it explicit in comments.

```go
// This implementation is deprecated due to its inefficiency.
// Please consider using `SendCommand` instead.
func (u *ReceiveUserMessageUseCase) SendNewCommand(
 ctx context.Context,
 cmdName string,
 message Message,
) error
```

### **6. Consistency Maintenance:**

- **Update Comments with Code Changes:** When you modify the code, ensure that related comments are updated accordingly.
- **Version-Specific Information:** Clearly state if a comment pertains to a specific version or circumstance.

Striking the right balance between self-explanatory code and targeted documentation is an art. The goal is to create code that is not only functional but also comprehensible to others who may encounter it. Well-maintained comments serve as a roadmap, guiding developers through the code and aiding in understanding its nuances.

## **Conclusion**

Investing time in creating good documentation is an investment in the success and sustainability of a software project. It enhances collaboration, accelerates onboarding, and contributes to the long-term maintainability of the codebase. As developers, let's prioritize the art of documentation to build software that not only works but is also understandable and sustainable over time.
