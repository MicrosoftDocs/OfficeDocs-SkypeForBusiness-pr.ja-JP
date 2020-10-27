---
title: 患者のアプリと EHR の統合 STU3 インターフェイス
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: 電子医療記録を Microsoft Teams の患者アプリと STU3 インターフェイス仕様に統合する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9282d6b6245b92a675c69ba1fcbf4ad726cdff62
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766900"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="574d4-103">STU3 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="574d4-103">STU3 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="574d4-104">**2020年10月30日の有効な患者アプリは廃止され、ユーザーは Teams app store からインストールできなくなります。今すぐ Teams の [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) を使い始めることをお勧めします。**</span><span class="sxs-lookup"><span data-stu-id="574d4-104">**Effective October 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="574d4-105">患者のアプリデータは、チームをバックアップする Office 365 グループのグループメールボックスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="574d4-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="574d4-106">患者のアプリが廃止されると、そのアプリに関連付けられたデータはすべてこのグループに保持されますが、ユーザーインターフェイスを使ってアクセスすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="574d4-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="574d4-107">現在のユーザーは、 [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使ってリストを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="574d4-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="574d4-108">[リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)は、すべての Teams ユーザー用にプレインストールされており、すべてのチームとチャネルでタブとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="574d4-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="574d4-109">リストを使用すると、正常性チームは、組み込みの [患者] テンプレートを使用して、最初から、または Excel にデータをインポートして、患者リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="574d4-109">With Lists, health teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="574d4-110">組織でのリストアプリの管理方法の詳細については、「 [リストアプリを管理](../../manage-lists-app.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="574d4-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="574d4-111">Microsoft Teams の患者と連携するように FHIR サーバーを設定または再構成するには、アプリがアクセスする必要があるデータを把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="574d4-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="574d4-112">FHIR サーバーでは、次のリソースについて、バンドルを使った POST 要求をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="574d4-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="574d4-113">診療</span><span class="sxs-lookup"><span data-stu-id="574d4-113">Patient</span></span>](#patient)
- [<span data-ttu-id="574d4-114">観察</span><span class="sxs-lookup"><span data-stu-id="574d4-114">Observation</span></span>](#observation)
- [<span data-ttu-id="574d4-115">状態</span><span class="sxs-lookup"><span data-stu-id="574d4-115">Condition</span></span>](#condition)
- [<span data-ttu-id="574d4-116">状況</span><span class="sxs-lookup"><span data-stu-id="574d4-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="574d4-117">Allergy Intolerance</span><span class="sxs-lookup"><span data-stu-id="574d4-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="574d4-118">サポート</span><span class="sxs-lookup"><span data-stu-id="574d4-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="574d4-119">[投薬ステートメント](#medication-request) (PATIENTSAPP の DSTU2 バージョンの MedicationOrder を置き換えます)</span><span class="sxs-lookup"><span data-stu-id="574d4-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="574d4-120">場所 (このリソースから必要な情報は、発生する可能性があります)</span><span class="sxs-lookup"><span data-stu-id="574d4-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="574d4-121">患者のリソースは唯一の必須リソースです (アプリがまったく読み込まれなくなります)。ただし、Microsoft Teams の患者アプリを使用して、最も優れたエンドユーザーエクスペリエンスを実現するために、以下に記載されている仕様ごとに、上記のすべてのリソースのサポートを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="574d4-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="574d4-122">複数のリソースの Microsoft Teams の患者アプリからのクエリは、FHIR サーバーの URL に対する要求のバンドル (バッチ) を投稿するものとします。</span><span class="sxs-lookup"><span data-stu-id="574d4-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="574d4-123">サーバーは各要求を処理し、各要求によって一致したリソースのバンドルを返します。</span><span class="sxs-lookup"><span data-stu-id="574d4-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="574d4-124">詳細と例については、「」を参照してください [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="574d4-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="574d4-125">機能ステートメント</span><span class="sxs-lookup"><span data-stu-id="574d4-125">Capability Statement</span></span>

<span data-ttu-id="574d4-126">最低限必要なフィールドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="574d4-126">These are the minimum required fields:</span></span>

 - <span data-ttu-id="574d4-127">後</span><span class="sxs-lookup"><span data-stu-id="574d4-127">REST</span></span>

    - <span data-ttu-id="574d4-128">モード</span><span class="sxs-lookup"><span data-stu-id="574d4-128">Mode</span></span>
    - <span data-ttu-id="574d4-129">通信</span><span class="sxs-lookup"><span data-stu-id="574d4-129">Interaction</span></span>
    - <span data-ttu-id="574d4-130">リソース: 種類</span><span class="sxs-lookup"><span data-stu-id="574d4-130">Resource: Type</span></span>
    - <span data-ttu-id="574d4-131">セキュリティ: [OAuth uri 用の拡張子](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="574d4-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="574d4-132">FhirVersion (コードは、どのバージョンをピボットするかを理解するために必要です。)</span><span class="sxs-lookup"><span data-stu-id="574d4-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="574d4-133">[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="574d4-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="574d4-134">診療</span><span class="sxs-lookup"><span data-stu-id="574d4-134">Patient</span></span>

<span data-ttu-id="574d4-135">以下は、Argonaut の患者プロファイルフィールドのサブセットである、必要な最小フィールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="574d4-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="574d4-136">名前。指定された</span><span class="sxs-lookup"><span data-stu-id="574d4-136">Name.Given</span></span>
 - <span data-ttu-id="574d4-137">家族</span><span class="sxs-lookup"><span data-stu-id="574d4-137">Name.Family</span></span>
 - <span data-ttu-id="574d4-138">女性</span><span class="sxs-lookup"><span data-stu-id="574d4-138">Gender</span></span>
 - <span data-ttu-id="574d4-139">地</span><span class="sxs-lookup"><span data-stu-id="574d4-139">BirthDate</span></span>
 - <span data-ttu-id="574d4-140">MRN (識別子)</span><span class="sxs-lookup"><span data-stu-id="574d4-140">MRN (Identifier)</span></span>

<span data-ttu-id="574d4-141">優れたユーザーエクスペリエンスを実現するために、 [Argonaut フィールド](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)に加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="574d4-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="574d4-142">名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="574d4-142">Name.Use</span></span>
 - <span data-ttu-id="574d4-143">名前プレフィックス</span><span class="sxs-lookup"><span data-stu-id="574d4-143">Name.Prefix</span></span>
 - <span data-ttu-id="574d4-144">[一般の専門スタッフ]-すべての専門スタッフ参照が患者リソースに含まれている必要があります (表示フィールドのみ)。</span><span class="sxs-lookup"><span data-stu-id="574d4-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="574d4-145">リソース検索では、/Patient/_search と次のパラメーターで POST メソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="574d4-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="574d4-146">id</span><span class="sxs-lookup"><span data-stu-id="574d4-146">id</span></span>
 - <span data-ttu-id="574d4-147">family = (ファミリ名に値が含まれているすべての患者を検索)</span><span class="sxs-lookup"><span data-stu-id="574d4-147">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="574d4-148">指定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="574d4-148">given=\<substring></span></span>
 - <span data-ttu-id="574d4-149">生年月日 = (完全一致)</span><span class="sxs-lookup"><span data-stu-id="574d4-149">birthdate=(exact match)</span></span>
 - <span data-ttu-id="574d4-150">性別 = (いずれかの管理者の性別の値)</span><span class="sxs-lookup"><span data-stu-id="574d4-150">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="574d4-151">\_count (返される結果の最大数)</span><span class="sxs-lookup"><span data-stu-id="574d4-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="574d4-152">応答には、 \_ 返されるレコードの数を制限するために、検索とカウントの結果として返されるレコードの合計数が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="574d4-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="574d4-153">識別子 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="574d4-153">identifier=\<mrn></span></span>

<span data-ttu-id="574d4-154">目標は、次のようにして患者の検索とフィルター処理を行うことができるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="574d4-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="574d4-155">ID: これは、FHIR のすべてのリソースが持つリソース ID です。</span><span class="sxs-lookup"><span data-stu-id="574d4-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="574d4-156">MRN: 診療員が知っている患者の実際の識別子です。</span><span class="sxs-lookup"><span data-stu-id="574d4-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="574d4-157">この MRN は、FHIR の識別子リソース内の識別子の種類に基づいています。</span><span class="sxs-lookup"><span data-stu-id="574d4-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="574d4-158">名前</span><span class="sxs-lookup"><span data-stu-id="574d4-158">Name</span></span>
- <span data-ttu-id="574d4-159">地</span><span class="sxs-lookup"><span data-stu-id="574d4-159">Birthdate</span></span>

<span data-ttu-id="574d4-160">次の通話の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="574d4-160">See the following example of the call:</span></span>

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=ruth&family=black

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "meta": {
    "lastUpdated": "2019-01-14T23:44:45.052+00:00"
  },
  "type": "searchset",
  "total": 1,
  "link": [
    {
      "relation": "self",
      "url": <fhir-server>/Patient/_search"
    }
  ],
  "entry": [
    {
      "fullUrl": <fhir-server>/Patient/<patient-id>",
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "meta": {
          "versionId": "1",
          "lastUpdated": "2017-10-18T18:32:37.000+00:00"
        },
        "text": {
          "status": "generated",
          "div": "<div>\n        <p>Ruth Black</p>\n      </div>"
        },
        "identifier": [
          {
            "use": "usual",
            "type": {
              "coding": [
                {
                  "system": "https://hl7.org/fhir/v2/0203",
                  "code": "MR",
                  "display": "Medical record number",
                  "userSelected": false
                }
              ],
              "text": "Medical record number"
            },
            "system": "http://hospital.smarthealthit.org",
            "value": "1234567"
          }
        ],
        "active": true,
        "name": [
          {
            "use": "official",
            "family": "Black",
            "given": [
              "Ruth",
              "C."
            ]
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "800-599-2739",
            "use": "home"
          },
          {
            "system": "phone",
            "value": "800-808-7785",
            "use": "mobile"
          },
          {
            "system": "email",
            "value": "ruth.black@example.com"
          }
        ],
        "gender": "female",
        "birthDate": "1951-08-23",
        "address": [
          {
            "use": "home",
            "line": [
              "26 South RdApt 22"
            ],
            "city": "Sapulpa",
            "state": "OK",
            "postalCode": "74066",
            "country": "USA"
          }
        ]
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

```
Request:
GET <fhir-server>/Patient/<patient-id>

Response:
{
  "resourceType": "Patient",
  "id": "<patient-id>",
  "identifier": [
    {
      "use": "usual",
      "type": {
        "coding": [
          {
            "system": "https://hl7.org/fhir/v2/0203",
            "code": "MR",
          }
        ],
        "text": "Medical record number"
      },
      "value": "1234567"
    }
  ],
  "name": [
    {
      "use": "official",
      "family": "Adams",
      "given": [ "Daniel", "X." ]
    }
  ],
  "gender": "male",
  "birthDate": "1925-12-23",
}
```

<span data-ttu-id="574d4-161">[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="574d4-161">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="574d4-162">観察</span><span class="sxs-lookup"><span data-stu-id="574d4-162">Observation</span></span>

<span data-ttu-id="574d4-163">これらは、 [Argonaut Vital-Signs プロファイル](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="574d4-163">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="574d4-164">発効 (日付と時刻)</span><span class="sxs-lookup"><span data-stu-id="574d4-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="574d4-165">コードの記述</span><span class="sxs-lookup"><span data-stu-id="574d4-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="574d4-166">Valu不定の値</span><span class="sxs-lookup"><span data-stu-id="574d4-166">ValueQuantity.Value</span></span>

<span data-ttu-id="574d4-167">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="574d4-167">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="574d4-168">コード。ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="574d4-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="574d4-169">Valuの単位</span><span class="sxs-lookup"><span data-stu-id="574d4-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="574d4-170">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="574d4-170">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="574d4-171">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="574d4-171">patient=\<patient id></span></span>
 - <span data-ttu-id="574d4-172">_sort =-date</span><span class="sxs-lookup"><span data-stu-id="574d4-172">_sort=-date</span></span>
 - <span data-ttu-id="574d4-173">category ("カテゴリ = バイタル-記号") を照会して、重要な記号の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="574d4-173">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="574d4-174">次の通話の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="574d4-174">Refer to this example of the call:</span></span>

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 20,
  "entry": [
    {
      "resource": {
        "resourceType": "Observation",
        "id": "<resource-id>",
        "category": [
          {
            "coding": [
              {
                "system": "https://hl7.org/fhir/observation-category",
                "code": "vital-signs"
              }
            ],
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "8867-4",
              "display": "heart_rate"
            }
          ]
        },
        "effectiveDateTime": "2009-04-08T00:00:00-06:00",
        "valueQuantity": {
          "value": 72.0,
          "unit": "{beats}/min",
          "system": "http://unitsofmeasure.org",
        }
      }
    },
    .
    .
    .
  ]
}
```

<span data-ttu-id="574d4-175">[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="574d4-175">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="574d4-176">状態</span><span class="sxs-lookup"><span data-stu-id="574d4-176">Condition</span></span>

<span data-ttu-id="574d4-177">[Argonaut 条件プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)のサブセットである最小必須フィールドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="574d4-177">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="574d4-178">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="574d4-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="574d4-179">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="574d4-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="574d4-180">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="574d4-180">AssertedDate</span></span>
 - <span data-ttu-id="574d4-181">程度</span><span class="sxs-lookup"><span data-stu-id="574d4-181">Severity</span></span>

<span data-ttu-id="574d4-182">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="574d4-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="574d4-183">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="574d4-183">patient=\<patient id></span></span>
 - <span data-ttu-id="574d4-184">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="574d4-184">_count=\<max results></span></span>

<span data-ttu-id="574d4-185">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="574d4-185">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 2,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "185903001",
              "display": "Needs influenza immunization",
            }
          ]
        },
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        },
        "assertedDate": "2018-04-04"
      }
    },
    .
    .
    .
  ]
}
```

<span data-ttu-id="574d4-186">[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="574d4-186">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="574d4-187">状況</span><span class="sxs-lookup"><span data-stu-id="574d4-187">Encounter</span></span>

<span data-ttu-id="574d4-188">" [US Core](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) " というプロファイルのサブセットである最小必須フィールドは、"フィールドが含まれている必要があります" である必要があります。</span><span class="sxs-lookup"><span data-stu-id="574d4-188">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="574d4-189">状態</span><span class="sxs-lookup"><span data-stu-id="574d4-189">Status</span></span>
 - <span data-ttu-id="574d4-190">[0] と入力します。コーディング [0]。表示</span><span class="sxs-lookup"><span data-stu-id="574d4-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="574d4-191">さらに、US Core の次のフィールドは、プロファイルの "サポートが必要" フィールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="574d4-191">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="574d4-192">期間. 開始日</span><span class="sxs-lookup"><span data-stu-id="574d4-192">Period.Start</span></span>
 - <span data-ttu-id="574d4-193">場所 [0]場所。表示</span><span class="sxs-lookup"><span data-stu-id="574d4-193">Location[0].Location.Display</span></span>

<span data-ttu-id="574d4-194">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="574d4-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="574d4-195">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="574d4-195">patient=\<patient id></span></span>
 - <span data-ttu-id="574d4-196">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="574d4-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="574d4-197">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="574d4-197">_count=\<max results></span></span>

<span data-ttu-id="574d4-198">目標は、患者の最後の既知の場所を取得できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="574d4-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="574d4-199">各検出は、位置情報リソースを参照します。</span><span class="sxs-lookup"><span data-stu-id="574d4-199">Each encounter references a location resource.</span></span> <span data-ttu-id="574d4-200">参照には、場所の表示フィールドも含まれます。</span><span class="sxs-lookup"><span data-stu-id="574d4-200">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="574d4-201">[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="574d4-201">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="574d4-202">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="574d4-202">AllergyIntolerance</span></span>

<span data-ttu-id="574d4-203">以下は、 [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="574d4-203">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="574d4-204">コード。テキスト</span><span class="sxs-lookup"><span data-stu-id="574d4-204">Code.Text</span></span>
 - <span data-ttu-id="574d4-205">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="574d4-205">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="574d4-206">ClinicalStatus/VerificationStatus (両方とも読む)</span><span class="sxs-lookup"><span data-stu-id="574d4-206">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="574d4-207">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリは次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="574d4-207">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="574d4-208">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="574d4-208">AssertedDate</span></span>
 - <span data-ttu-id="574d4-209">注テキスト</span><span class="sxs-lookup"><span data-stu-id="574d4-209">Note.Text</span></span>
 - <span data-ttu-id="574d4-210">反</span><span class="sxs-lookup"><span data-stu-id="574d4-210">Reaction</span></span>
    - <span data-ttu-id="574d4-211">物質 (1 つのコーディング要素)</span><span class="sxs-lookup"><span data-stu-id="574d4-211">Substance (one coding element)</span></span>
    - <span data-ttu-id="574d4-212">影響 (1 つのコード要素)</span><span class="sxs-lookup"><span data-stu-id="574d4-212">Manifestation (one coding element)</span></span>

<span data-ttu-id="574d4-213">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="574d4-213">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="574d4-214">患者 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="574d4-214">Patient =  \<patient id></span></span>

<span data-ttu-id="574d4-215">次の通話の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="574d4-215">See the following example of the call:</span></span> 

```
Request:
GET <fhir-server>/AllergyIntolerance?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "AllergyIntolerance",
        "id": "<resource-id>",
        "clinicalStatus": "active",
        "verificationStatus": "confirmed",
        "code": {
          "coding": [
            {
              "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",
              "code": "N0000175503",
              "display": "sulfonamide antibacterial",
            }
          ],
          "text": "sulfonamide antibacterial"
        },
        "assertedDate": "2018-01-01T00:00:00-07:00",
        "reaction": [
          {
            "manifestation": [
              {
                "coding": [
                  {
                    "system": "http://snomed.info/sct",
                    "code": "271807003",
                    "display": "skin rash",
                  }
                ],
                "text": "skin rash"
              }
            ],
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="574d4-216">[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="574d4-216">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="574d4-217">投薬要求</span><span class="sxs-lookup"><span data-stu-id="574d4-217">Medication Request</span></span>

<span data-ttu-id="574d4-218">以下は、 [US Core 投薬要求プロファイル](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="574d4-218">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="574d4-219">投薬 (参照の場合)</span><span class="sxs-lookup"><span data-stu-id="574d4-219">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="574d4-220">投薬 (CodableConcept の場合)</span><span class="sxs-lookup"><span data-stu-id="574d4-220">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="574d4-221">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="574d4-221">AuthoredOn</span></span>
 - <span data-ttu-id="574d4-222">要求者。ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="574d4-222">Requester.Agent.Display</span></span>

<span data-ttu-id="574d4-223">優れたユーザーエクスペリエンスを実現するには、米国内のコアフィールドに加えて、患者のアプリでも次のフィールドを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="574d4-223">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="574d4-224">DosageInstruction [..]テキスト</span><span class="sxs-lookup"><span data-stu-id="574d4-224">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="574d4-225">テキスト</span><span class="sxs-lookup"><span data-stu-id="574d4-225">Text</span></span>

<span data-ttu-id="574d4-226">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="574d4-226">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="574d4-227">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="574d4-227">patient=\<patient id></span></span>
 - <span data-ttu-id="574d4-228">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="574d4-228">_count=\<max results></span></span>

<span data-ttu-id="574d4-229">[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="574d4-229">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="574d4-230">サポート</span><span class="sxs-lookup"><span data-stu-id="574d4-230">Coverage</span></span>

<span data-ttu-id="574d4-231">以下は、US Core または Argonaut のプロファイルでカバーされていない最低限の必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="574d4-231">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="574d4-232">グループ化、少なくとも1つの要素を</span><span class="sxs-lookup"><span data-stu-id="574d4-232">Grouping, at least one element with</span></span>
    - <span data-ttu-id="574d4-233">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="574d4-233">GroupDisplay</span></span>
    - <span data-ttu-id="574d4-234">Plan ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="574d4-234">PlanDisplay</span></span>
 - <span data-ttu-id="574d4-235">ピリオド</span><span class="sxs-lookup"><span data-stu-id="574d4-235">Period</span></span>
 - <span data-ttu-id="574d4-236">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="574d4-236">SubscriberId</span></span>

<span data-ttu-id="574d4-237">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="574d4-237">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="574d4-238">患者 = \<patient id></span><span class="sxs-lookup"><span data-stu-id="574d4-238">Patient = \<patient id></span></span>

<span data-ttu-id="574d4-239">[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="574d4-239">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
