# Temporary Maintenance Fork: php-fhir-model Fixes

This repository is a **temporary fork** of the official `luscii/php-fhir-model` package.

I am using this fork to apply a critical bug fix required for my projects while awaiting the official update from the original maintainers.

## 🛠️ Included Fix

This fork includes a patch to address a compatibility issue with recent PHP versions:

### PHP Deprecated Notices for `jsonSerialize()`

**Problem:** Running the library on modern PHP versions (e.g., PHP 8.1+) results in numerous `PHP Deprecated` notices because the `jsonSerialize()` method in various classes lacks the required return type declaration.

**Correction:** The `jsonSerialize()` methods have been updated across all affected classes to explicitly include the **`: mixed`** return type, ensuring compatibility with the `JsonSerializable` interface and suppressing the deprecated notices.

## ⚠️ WARNING / TEMPORARY USE ONLY

* **Do NOT use this repository as a long-term dependency.**
* This fork is solely intended to hold the immediate fix and will **NOT** be actively maintained with new features.
* **Action Required:** Once the official `luscii/php-fhir-model` repository merges the fix and releases a new version, you must switch back to the original package immediately.

## 🔗 Original Project & Credit

All credit and intellectual property for the original code belong to the creators of the original project.

| Detail | Value |
| :--- | :--- |
| **Original Vendor/Package:** | `luscii/php-fhir-model` |
| **Original GitHub Repository:** | `https://github.com/luscii/php-fhir-model` |

## How to Use This Fork in Composer

To temporarily use this fixed version in your project, modify your `composer.json` by adding this repository as a custom VCS repository and requiring the specific branch where the fix resides:

```json
{
    "repositories": [
        {
            "type": "vcs",
            "url": "[https://github.com/SEU_USUARIO/php-fhir-model](https://github.com/SEU_USUARIO/php-fhir-model)" 
        }
    ],
    "require": {
        "luscii/php-fhir-model": "dev-sua-branch-com-a-correcao" 
        // Example: "dev-fix-jsonserialize"
    }
}