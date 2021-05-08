---
title: Patients App and EHR integration STU3 interface
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
description: Microsoft Teams Patients アプリと STU3 インターフェイスの仕様に電子健康記録を統合する方法について説明します。
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803495"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="9ef12-103">STU3 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="9ef12-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="9ef12-104">2020 年 10 月 30 日より、患者アプリは廃止され、Teams の[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="9ef12-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="9ef12-105">患者アプリのデータは、チームを支援する Office 365 グループのグループ メールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="9ef12-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="9ef12-106">患者アプリに関連付けられているすべてのデータはこのグループに保持されますが、ユーザー インターフェイスからアクセスすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="9ef12-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="9ef12-107">ユーザーは、[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使用してリストを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="9ef12-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="9ef12-108">リストを使用すると、医療機関のケア チームは、ラウンドや学際的なチーム会議から一般的な患者の監視に至るまでのシナリオで患者リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9ef12-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="9ef12-109">開始するには、リストの患者テンプレートを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9ef12-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="9ef12-110">組織でリスト アプリを管理する方法の詳細については、「[リスト アプリの管理](../../manage-lists-app.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ef12-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="9ef12-111">Microsoft Teams Patients アプリで動作する FHIR サーバーを設定または再構成するには、アプリがアクセスする必要があるデータを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ef12-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="9ef12-112">FHIR サーバーは、次のリソースのバンドルを使用した POST 要求をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ef12-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="9ef12-113">患者</span><span class="sxs-lookup"><span data-stu-id="9ef12-113">Patient</span></span>](#patient)
- [<span data-ttu-id="9ef12-114">観察</span><span class="sxs-lookup"><span data-stu-id="9ef12-114">Observation</span></span>](#observation)
- [<span data-ttu-id="9ef12-115">状態</span><span class="sxs-lookup"><span data-stu-id="9ef12-115">Condition</span></span>](#condition)
- [<span data-ttu-id="9ef12-116">Encounter</span><span class="sxs-lookup"><span data-stu-id="9ef12-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="9ef12-117">取り込み中の容容性</span><span class="sxs-lookup"><span data-stu-id="9ef12-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="9ef12-118">対象範囲</span><span class="sxs-lookup"><span data-stu-id="9ef12-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="9ef12-119">[お薬に](#medication-request) 関する声明 (DSTU2 バージョンの PatientsApp のOrder を置き換える)</span><span class="sxs-lookup"><span data-stu-id="9ef12-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="9ef12-120">場所 (このリソースに必要な情報は Encounter に含まれます)</span><span class="sxs-lookup"><span data-stu-id="9ef12-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="9ef12-121">Patient リソースは唯一の必須リソースです (アプリが読み込めずに)。ただし、パートナーは、以下に示す仕様に従って上記のすべてのリソースのサポートを実装し、Microsoft Teams Patients アプリを使用した最適なエクスペリエンスを実現Microsoft Teams勧めします。</span><span class="sxs-lookup"><span data-stu-id="9ef12-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="9ef12-122">Microsoft Teams Patients アプリからの複数のリソースに対するクエリは、FHIR サーバーの URL に要求のバンドル (BATCH) を投稿する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ef12-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="9ef12-123">サーバーは各要求を処理し、各要求に一致するリソースのバンドルを返します。</span><span class="sxs-lookup"><span data-stu-id="9ef12-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="9ef12-124">詳細と例については、 を参照してください [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="9ef12-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="9ef12-125">Capability ステートメント</span><span class="sxs-lookup"><span data-stu-id="9ef12-125">Capability Statement</span></span>

<span data-ttu-id="9ef12-126">必須の最小フィールドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="9ef12-126">These are the minimum required fields:</span></span>

 - <span data-ttu-id="9ef12-127">REST</span><span class="sxs-lookup"><span data-stu-id="9ef12-127">REST</span></span>

    - <span data-ttu-id="9ef12-128">モード</span><span class="sxs-lookup"><span data-stu-id="9ef12-128">Mode</span></span>
    - <span data-ttu-id="9ef12-129">対話</span><span class="sxs-lookup"><span data-stu-id="9ef12-129">Interaction</span></span>
    - <span data-ttu-id="9ef12-130">リソース: 型</span><span class="sxs-lookup"><span data-stu-id="9ef12-130">Resource: Type</span></span>
    - <span data-ttu-id="9ef12-131">セキュリティ: [OAuth URI の拡張機能](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="9ef12-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="9ef12-132">FhirVersion (このコードでは、ピボットするバージョンを理解するためにこれを必要とします)。</span><span class="sxs-lookup"><span data-stu-id="9ef12-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="9ef12-133">この [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) フィールド セットのその他の詳細については、 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ef12-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="9ef12-134">患者</span><span class="sxs-lookup"><span data-stu-id="9ef12-134">Patient</span></span>

<span data-ttu-id="9ef12-135">Argonaut 患者プロファイル フィールドのサブセットである最小必須フィールドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="9ef12-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="9ef12-136">Name.Given</span><span class="sxs-lookup"><span data-stu-id="9ef12-136">Name.Given</span></span>
 - <span data-ttu-id="9ef12-137">Name.Family</span><span class="sxs-lookup"><span data-stu-id="9ef12-137">Name.Family</span></span>
 - <span data-ttu-id="9ef12-138">性別</span><span class="sxs-lookup"><span data-stu-id="9ef12-138">Gender</span></span>
 - <span data-ttu-id="9ef12-139">BirthDate</span><span class="sxs-lookup"><span data-stu-id="9ef12-139">BirthDate</span></span>
 - <span data-ttu-id="9ef12-140">MRN (識別子)</span><span class="sxs-lookup"><span data-stu-id="9ef12-140">MRN (Identifier)</span></span>

<span data-ttu-id="9ef12-141">[Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)フィールドに加えて、患者アプリは次のフィールドを読み取って、ユーザー エクスペリエンスを向上できます。</span><span class="sxs-lookup"><span data-stu-id="9ef12-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="9ef12-142">Name.Use</span><span class="sxs-lookup"><span data-stu-id="9ef12-142">Name.Use</span></span>
 - <span data-ttu-id="9ef12-143">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="9ef12-143">Name.Prefix</span></span>
 - <span data-ttu-id="9ef12-144">[GeneralPractitioner] - GeneralPractitioner の参照は、患者リソースに含める必要があります (表示フィールドのみ)</span><span class="sxs-lookup"><span data-stu-id="9ef12-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="9ef12-145">リソース検索では、/Patient/_search の POST メソッドと次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ef12-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="9ef12-146">id</span><span class="sxs-lookup"><span data-stu-id="9ef12-146">id</span></span>
 - <span data-ttu-id="9ef12-147">family=(ファミリ名に値が含まれるすべての患者を検索します)</span><span class="sxs-lookup"><span data-stu-id="9ef12-147">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="9ef12-148">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="9ef12-148">given=\<substring></span></span>
 - <span data-ttu-id="9ef12-149">birthdate=(完全一致)</span><span class="sxs-lookup"><span data-stu-id="9ef12-149">birthdate=(exact match)</span></span>
 - <span data-ttu-id="9ef12-150">gender=(管理性別の 1 つである値)</span><span class="sxs-lookup"><span data-stu-id="9ef12-150">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="9ef12-151">\_count (返される結果の最大数)</span><span class="sxs-lookup"><span data-stu-id="9ef12-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="9ef12-152">応答には、検索の結果として返されるレコードの総数が含まれている必要があります。返されるレコードの数を制限するために、PatientsApp によってカウントが \_ 使用されます。</span><span class="sxs-lookup"><span data-stu-id="9ef12-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="9ef12-153">identifier=\<mrn></span><span class="sxs-lookup"><span data-stu-id="9ef12-153">identifier=\<mrn></span></span>

<span data-ttu-id="9ef12-154">目標は、次の方法で患者を検索してフィルター処理できる状態に設定します。</span><span class="sxs-lookup"><span data-stu-id="9ef12-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="9ef12-155">ID: これは、FHIR のすべてのリソースが持つリソース ID です。</span><span class="sxs-lookup"><span data-stu-id="9ef12-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="9ef12-156">MRN: これは、医療スタッフが知る患者の実際の識別子です。</span><span class="sxs-lookup"><span data-stu-id="9ef12-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="9ef12-157">この MRN は、FHIR の識別子リソース内の識別子の種類に基づくと理解しています。</span><span class="sxs-lookup"><span data-stu-id="9ef12-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="9ef12-158">名前</span><span class="sxs-lookup"><span data-stu-id="9ef12-158">Name</span></span>
- <span data-ttu-id="9ef12-159">生年月日</span><span class="sxs-lookup"><span data-stu-id="9ef12-159">Birthdate</span></span>

<span data-ttu-id="9ef12-160">呼び出しの次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ef12-160">See the following example of the call:</span></span>

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

<span data-ttu-id="9ef12-161">この [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) フィールド セットのその他の詳細については、 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ef12-161">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="9ef12-162">観察</span><span class="sxs-lookup"><span data-stu-id="9ef12-162">Observation</span></span>

<span data-ttu-id="9ef12-163">これらは必須の最小フィールドです。これは、Argonaut プロファイルの [サブセットVital-Signsです](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)。</span><span class="sxs-lookup"><span data-stu-id="9ef12-163">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="9ef12-164">有効 (日付の時刻または期間)</span><span class="sxs-lookup"><span data-stu-id="9ef12-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="9ef12-165">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="9ef12-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="9ef12-166">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="9ef12-166">ValueQuantity.Value</span></span>

<span data-ttu-id="9ef12-167">Argonaut フィールドに加えて、ユーザー エクスペリエンスを向上するために、Patients アプリは次のフィールドも読み取り可能です。</span><span class="sxs-lookup"><span data-stu-id="9ef12-167">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="9ef12-168">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="9ef12-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="9ef12-169">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="9ef12-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="9ef12-170">リソース検索では、GET メソッドと次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ef12-170">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="9ef12-171">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="9ef12-171">patient=\<patient id></span></span>
 - <span data-ttu-id="9ef12-172">_sort=-date</span><span class="sxs-lookup"><span data-stu-id="9ef12-172">_sort=-date</span></span>
 - <span data-ttu-id="9ef12-173">category ("category=vital-signs" をクエリして、バイタル サインの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="9ef12-173">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="9ef12-174">呼び出しの次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ef12-174">Refer to this example of the call:</span></span>

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

<span data-ttu-id="9ef12-175">この [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) フィールド セットのその他の詳細については、 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ef12-175">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="9ef12-176">状態</span><span class="sxs-lookup"><span data-stu-id="9ef12-176">Condition</span></span>

<span data-ttu-id="9ef12-177">Argonaut 条件プロファイルのサブセットである最小必須 [フィールドを次に示します](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)。</span><span class="sxs-lookup"><span data-stu-id="9ef12-177">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="9ef12-178">Code.Coding[0].表示</span><span class="sxs-lookup"><span data-stu-id="9ef12-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="9ef12-179">Argonaut フィールドに加えて、ユーザー エクスペリエンスを向上するために、Patients アプリは次のフィールドも読み取り可能です。</span><span class="sxs-lookup"><span data-stu-id="9ef12-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="9ef12-180">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="9ef12-180">AssertedDate</span></span>
 - <span data-ttu-id="9ef12-181">重大度</span><span class="sxs-lookup"><span data-stu-id="9ef12-181">Severity</span></span>

<span data-ttu-id="9ef12-182">リソース検索では、GET メソッドと次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ef12-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="9ef12-183">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="9ef12-183">patient=\<patient id></span></span>
 - <span data-ttu-id="9ef12-184">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="9ef12-184">_count=\<max results></span></span>

<span data-ttu-id="9ef12-185">この呼び出しの次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ef12-185">See the following example of this call:</span></span>

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

<span data-ttu-id="9ef12-186">この [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) フィールド セットのその他の詳細については、 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ef12-186">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="9ef12-187">Encounter</span><span class="sxs-lookup"><span data-stu-id="9ef12-187">Encounter</span></span>

<span data-ttu-id="9ef12-188">これらは、US [Core Encounter](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) プロファイルの "必要な" フィールドのサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="9ef12-188">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="9ef12-189">状態</span><span class="sxs-lookup"><span data-stu-id="9ef12-189">Status</span></span>
 - <span data-ttu-id="9ef12-190">「[0]」と入力します。Coding[0].表示</span><span class="sxs-lookup"><span data-stu-id="9ef12-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="9ef12-191">さらに、US Core Encounter プロファイルの "サポートが必要" フィールドの次のフィールドも表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ef12-191">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="9ef12-192">Period.Start</span><span class="sxs-lookup"><span data-stu-id="9ef12-192">Period.Start</span></span>
 - <span data-ttu-id="9ef12-193">Location[0].Location.Display</span><span class="sxs-lookup"><span data-stu-id="9ef12-193">Location[0].Location.Display</span></span>

<span data-ttu-id="9ef12-194">リソース検索では、GET メソッドと次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ef12-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="9ef12-195">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="9ef12-195">patient=\<patient id></span></span>
 - <span data-ttu-id="9ef12-196">_sort:desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="9ef12-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="9ef12-197">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="9ef12-197">_count=\<max results></span></span>

<span data-ttu-id="9ef12-198">目標は、患者の最後の既知の場所を取得できる点です。</span><span class="sxs-lookup"><span data-stu-id="9ef12-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="9ef12-199">各エンカウンターは、場所リソースを参照します。</span><span class="sxs-lookup"><span data-stu-id="9ef12-199">Each encounter references a location resource.</span></span> <span data-ttu-id="9ef12-200">参照には、場所の表示フィールドも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ef12-200">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="9ef12-201">この [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) フィールド セットのその他の詳細については、 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ef12-201">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="9ef12-202">分性Intolerance</span><span class="sxs-lookup"><span data-stu-id="9ef12-202">AllergyIntolerance</span></span>

<span data-ttu-id="9ef12-203">次に示すのは必須の最小フィールドです。 [これは、Argonautいしなやかプロファイルのサブセット](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) です。</span><span class="sxs-lookup"><span data-stu-id="9ef12-203">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="9ef12-204">Code.Text</span><span class="sxs-lookup"><span data-stu-id="9ef12-204">Code.Text</span></span>
 - <span data-ttu-id="9ef12-205">Code.Coding[0].表示</span><span class="sxs-lookup"><span data-stu-id="9ef12-205">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="9ef12-206">ClinicalStatus/VerificationStatus (両方を読み取る)</span><span class="sxs-lookup"><span data-stu-id="9ef12-206">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="9ef12-207">Argonaut フィールドに加えて、ユーザー エクスペリエンスを向上するために、Patients アプリは次のフィールドも読み取り可能です。</span><span class="sxs-lookup"><span data-stu-id="9ef12-207">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="9ef12-208">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="9ef12-208">AssertedDate</span></span>
 - <span data-ttu-id="9ef12-209">Note.Text</span><span class="sxs-lookup"><span data-stu-id="9ef12-209">Note.Text</span></span>
 - <span data-ttu-id="9ef12-210">リアクション</span><span class="sxs-lookup"><span data-stu-id="9ef12-210">Reaction</span></span>
    - <span data-ttu-id="9ef12-211">Substance (1 つのコーディング要素)</span><span class="sxs-lookup"><span data-stu-id="9ef12-211">Substance (one coding element)</span></span>
    - <span data-ttu-id="9ef12-212">症状 (1 つのコーディング要素)</span><span class="sxs-lookup"><span data-stu-id="9ef12-212">Manifestation (one coding element)</span></span>

<span data-ttu-id="9ef12-213">リソース検索では、GET メソッドと次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ef12-213">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="9ef12-214">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="9ef12-214">Patient =  \<patient id></span></span>

<span data-ttu-id="9ef12-215">呼び出しの次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ef12-215">See the following example of the call:</span></span> 

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

<span data-ttu-id="9ef12-216">この [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) フィールド セットのその他の詳細については、 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ef12-216">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="9ef12-217">薬の要求</span><span class="sxs-lookup"><span data-stu-id="9ef12-217">Medication Request</span></span>

<span data-ttu-id="9ef12-218">これらは必須の最小フィールドです。これは [、US Coreの核薬要求プロファイルのサブセットです](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)。</span><span class="sxs-lookup"><span data-stu-id="9ef12-218">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="9ef12-219">しだい.Display (参考の場合)</span><span class="sxs-lookup"><span data-stu-id="9ef12-219">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="9ef12-220">(CodableConcept の場合)</span><span class="sxs-lookup"><span data-stu-id="9ef12-220">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="9ef12-221">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="9ef12-221">AuthoredOn</span></span>
 - <span data-ttu-id="9ef12-222">Requester.Agent.Display</span><span class="sxs-lookup"><span data-stu-id="9ef12-222">Requester.Agent.Display</span></span>

<span data-ttu-id="9ef12-223">US Core フィールドに加えて、ユーザー エクスペリエンスを向上するために、Patients アプリは次のフィールドも読み取り可能です。</span><span class="sxs-lookup"><span data-stu-id="9ef12-223">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="9ef12-224">ストラクター [...]。テキスト</span><span class="sxs-lookup"><span data-stu-id="9ef12-224">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="9ef12-225">テキスト</span><span class="sxs-lookup"><span data-stu-id="9ef12-225">Text</span></span>

<span data-ttu-id="9ef12-226">リソース検索では、GET メソッドと次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ef12-226">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="9ef12-227">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="9ef12-227">patient=\<patient id></span></span>
 - <span data-ttu-id="9ef12-228">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="9ef12-228">_count=\<max results></span></span>

<span data-ttu-id="9ef12-229">この [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) フィールド セットのその他の詳細については、 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ef12-229">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="9ef12-230">対象範囲</span><span class="sxs-lookup"><span data-stu-id="9ef12-230">Coverage</span></span>

<span data-ttu-id="9ef12-231">これらは必須の最小フィールドで、US Core プロファイルまたは Argonaut プロファイルの対象外です。</span><span class="sxs-lookup"><span data-stu-id="9ef12-231">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="9ef12-232">グループ化、少なくとも 1 つの要素</span><span class="sxs-lookup"><span data-stu-id="9ef12-232">Grouping, at least one element with</span></span>
    - <span data-ttu-id="9ef12-233">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="9ef12-233">GroupDisplay</span></span>
    - <span data-ttu-id="9ef12-234">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="9ef12-234">PlanDisplay</span></span>
 - <span data-ttu-id="9ef12-235">期間</span><span class="sxs-lookup"><span data-stu-id="9ef12-235">Period</span></span>
 - <span data-ttu-id="9ef12-236">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="9ef12-236">SubscriberId</span></span>

<span data-ttu-id="9ef12-237">リソース検索では、GET メソッドと次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ef12-237">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="9ef12-238">Patient = \<patient id></span><span class="sxs-lookup"><span data-stu-id="9ef12-238">Patient = \<patient id></span></span>

<span data-ttu-id="9ef12-239">この [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) フィールド セットのその他の詳細については、 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ef12-239">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
