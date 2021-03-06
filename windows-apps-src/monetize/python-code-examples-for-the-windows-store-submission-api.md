---
author: mcleanbyron
ms.assetid: 8AC56AAF-8D8C-4193-A6B3-BB5D0669D994
description: Use the Python code examples in this section to learn more about using the Windows Store submission API.
title: Python code examples for the Windows Store submission API
ms.author: mcleans
ms.date: 02/08/2017
ms.topic: article
ms.prod: windows
ms.technology: uwp
keywords: windows 10, uwp, Windows Store submission API, code examples
---

# Python code examples for the Windows Store submission API

This article provides Python code examples for using the *Windows Store submission API*. For more information about this API, see [Create and manage submissions using Windows Store services](create-and-manage-submissions-using-windows-store-services.md).

These code examples demonstrate the following tasks:

* [Obtain an Azure AD access token](#token)
* [Create an add-on](#create-add-on)
* [Create a package flight](#create-package-flight)
* [Create an app submission](#create-app-submission)
* [Create an add-on submission](#create-add-on-submission)
* [Create a package flight submission](#create-flight-submission)

<span id="token" />
## Obtain an Azure AD access token

The following example demonstrates how to [obtain an Azure AD access token](create-and-manage-submissions-using-windows-store-services.md#obtain-an-azure-ad-access-token) that you can use to call methods in the Windows Store submission API. After you obtain a token, you have 60 minutes to use this token in calls to the Windows Store submission API before the token expires. After the token expires, you can generate a new token..

[!code[SubmissionApi](./code/StoreServicesExamples_Submission/python/Examples.py#L1-L20)]

<span id="create-add-on" />
## Create an add-on

The following example demonstrates how to [create](create-an-add-on.md) and then [delete](delete-an-add-on.md) an add-on (add-ons are also known as in-app products or IAPs).

[!code[SubmissionApi](./code/StoreServicesExamples_Submission/python/Examples.py#L26-L52)]

<span id="create-package-flight" />
## Create a package flight

The following example demonstrates how to [create](create-a-flight.md) and then [delete](delete-a-flight.md) a package flight.

[!code[SubmissionApi](./code/StoreServicesExamples_Submission/python/Examples.py#L58-L87)]

<span id="create-app-submission" />
## Create an app submission

The following example shows how to use several methods in the Windows Store submission API to create an app submission. To do this, the code creates a new submission as a clone of the last published submission, and then updates and commits the cloned submission to Windows Dev Center. Specifically, the example performs these tasks:

1. To begin, the example [gets data for the specified app](get-an-app.md).
2. Next, it [deletes the pending submission for the app](delete-an-app-submission.md), if one exists.
3. It then [creates a new submission for the app](create-an-app-submission.md) (the new submission is a copy of the last published submission).
4. It changes some details for the new submission and upload a new package for the submission to Azure Blob storage.
5. Next, it [updates](update-an-app-submission.md) and then [commits](commit-an-app-submission.md) the new submission to Windows Dev Center.
6. Finally, it periodically [checks the status of the new submission](get-status-for-an-app-submission.md) until the submission is successfully committed.

[!code[SubmissionApi](./code/StoreServicesExamples_Submission/python/Examples.py#L93-L166)]

<span id="create-add-on-submission" />
## Create an add-on submission

The following example shows how to use several methods in the Windows Store submission API to create an add-on submission. To do this, the code creates a new submission as a clone of the last published submission, and then updates and commits the cloned submission to Windows Dev Center. Specifically, the example performs these tasks:

1. To begin, the example [gets data for the specified add-on](get-an-add-on.md).
2. Next, it [deletes the pending submission for the add-on](delete-an-add-on-submission.md), if one exists.
3. It then [creates a new submission for the add-on](create-an-add-on-submission.md) (the new submission is a copy of the last published submission).
4. It uploads a ZIP archive that contains icons for the submission to Azure Blob storage. For more information, see the relevant instructions about uploading a ZIP archive to Azure Blob storage in [Create an add-on submission](manage-add-on-submissions.md#create-an-add-on-submission).
5. Next, it [updates](update-an-add-on-submission.md) and then [commits](commit-an-add-on-submission.md) the new submission to Windows Dev Center.
6. Finally, it periodically [checks the status of the new submission](get-status-for-an-add-on-submission.md) until the submission is successfully committed.

[!code[SubmissionApi](./code/StoreServicesExamples_Submission/python/Examples.py#L172-L245)]

<span id="create-flight-submission" />
## Create a package flight submission

The following example shows how to use several methods in the Windows Store submission API to create a package flight submission. To do this, the code creates a new submission as a clone of the last published submission, and then updates and commits the cloned submission to Windows Dev Center. Specifically, the example performs these tasks:

1. To begin, the example [gets data for the specified package flight](get-a-flight.md).
2. Next, it [deletes the pending submission for the package flight](delete-a-flight-submission.md), if one exists.
3. It then [creates a new submission for the package flight](create-a-flight-submission.md) (the new submission is a copy of the last published submission).
4. It uploads a new package for the submission to Azure Blob storage. For more information, see the relevant instructions about uploading a ZIP archive to Azure Blob storage in [Create a package flight submission](manage-flight-submissions.md#create-a-package-flight-submission).
5. Next, it [updates](update-a-flight-submission.md) and then [commits](commit-a-flight-submission.md) the new submission to Windows Dev Center.
6. Finally, it periodically [checks the status of the new submission](get-status-for-a-flight-submission.md) until the submission is successfully committed.

[!code[SubmissionApi](./code/StoreServicesExamples_Submission/python/Examples.py#L251-L325)]

## Related topics

* [Create and manage submissions using Windows Store services](create-and-manage-submissions-using-windows-store-services.md)
