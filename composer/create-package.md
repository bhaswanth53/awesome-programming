# How to create package in composer?

Publishing a PHP package to Composer (via [Packagist](https://packagist.org)) involves several steps, from creating the package to making it available for others to install. Here's a detailed step-by-step guide:

---

## **Step 1: Create Your PHP Package**

1. **Organize Your Code**
   - Create a folder structure for your package:
     ```
     framework/
         src/
             SomeClass.php
         tests/
         composer.json
         README.md
         LICENSE
     ```
   - Ensure your PHP files are inside the `src/` folder or another directory of your choice.

2. **Write Your PHP Code**
   - Example: `framework/src/SomeClass.php`
     ```php
     <?php

     namespace VendorName\Framework;

     class SomeClass {
         public function doSomething() {
             return "Hello, Composer!";
         }
     }
     ```

---

## **Step 2: Initialize Composer**

1. **Create a `composer.json` File**
   - Navigate to the `framework` directory and run:
     ```bash
     composer init
     ```
   - Follow the prompts to provide:
     - Package name (e.g., `vendor-name/framework`).
     - Description.
     - Author(s).
     - Minimum stability (default: `stable`).
     - License (e.g., `MIT`).

   - Example `composer.json`:
     ```json
     {
       "name": "vendor-name/framework",
       "description": "A simple PHP framework library.",
       "type": "library",
       "license": "MIT",
       "autoload": {
         "psr-4": {
           "VendorName\\Framework\\": "src/"
         }
       },
       "require": {
         "php": ">=7.4"
       }
     }
     ```

2. **Test Autoloading**
   - Run `composer dump-autoload` to generate the autoloader.
   - Test your package:
     ```php
     require 'vendor/autoload.php';

     use VendorName\Framework\SomeClass;

     $obj = new SomeClass();
     echo $obj->doSomething();
     ```

---

## **Step 3: Add a Version Control System**

1. **Initialize a Git Repository**
   - Inside the `framework` directory, run:
     ```bash
     git init
     git add .
     git commit -m "Initial commit"
     ```

2. **Push the Code to a Remote Repository**
   - Create a repository on GitHub (or another Git hosting service).
   - Link your local repository:
     ```bash
     git remote add origin https://github.com/your-username/framework.git
     git branch -M main
     git push -u origin main
     ```

---

## **Step 4: Publish the Package to Packagist**

1. **Create a Packagist Account**
   - Sign up at [Packagist](https://packagist.org/).

2. **Submit Your Package**
   - Go to [Submit Package](https://packagist.org/packages/submit).
   - Provide the GitHub repository URL of your package.
   - Packagist will validate the repository and fetch the `composer.json` file.

3. **Add a Webhook (For Automatic Updates)**
   - Packagist will prompt you to add a webhook to your GitHub repository.
   - This ensures Packagist automatically updates whenever you push changes.

---

## **Step 5: Test Installation**

1. **Install the Package in a Test Project**
   - In a separate project, run:
     ```bash
     composer require vendor-name/framework
     ```

2. **Use the Package**
   - Example:
     ```php
     require 'vendor/autoload.php';

     use VendorName\Framework\SomeClass;

     $obj = new SomeClass();
     echo $obj->doSomething();
     ```

---

## **Step 6: Maintain Your Package**

1. **Tag Releases**
   - Use Git tags to version your package. For example:
     ```bash
     git tag v1.0.0
     git push origin v1.0.0
     ```
   - Packagist will detect the tag and make it available as a new version.

2. **Update Your Package**
   - Push changes to the repository and update the version by tagging it:
     ```bash
     git add .
     git commit -m "Added new feature"
     git tag v1.1.0
     git push origin v1.1.0
     ```

3. **Respond to Issues**
   - Monitor and respond to issues or pull requests on GitHub.

---

### **Checklist**
- ✅ Code is inside `src/`.
- ✅ `composer.json` is valid.
- ✅ Hosted on a Git repository (e.g., GitHub).
- ✅ Published to Packagist.
- ✅ Installed and tested in a project.

Let me know if you need help with any specific step!