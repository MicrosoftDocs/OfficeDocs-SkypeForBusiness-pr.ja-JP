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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a36c6176b4873dd41d654493bd36e9a3dbbfd49a
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772268"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="80df0-103">STU3 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="80df0-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="80df0-104">2020年10月30日の有効な患者アプリは廃止され、Teams の [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) で置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="80df0-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="80df0-105">リストを使用すると、医療機関のケアチームは、ラウンドやさまざまなチーム会議から一般的な患者の監視までのシナリオのために患者リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="80df0-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="80df0-106">始めるには、「患者」のテンプレートをリストから選びます。</span><span class="sxs-lookup"><span data-stu-id="80df0-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="80df0-107">組織でのリストアプリの管理方法の詳細については、「 [リストアプリを管理](../../manage-lists-app.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80df0-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="80df0-108">Microsoft Teams の患者と連携するように FHIR サーバーを設定または再構成するには、アプリがアクセスする必要があるデータを把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80df0-108">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="80df0-109">FHIR サーバーでは、次のリソースについて、バンドルを使った POST 要求をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="80df0-109">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="80df0-110">診療</span><span class="sxs-lookup"><span data-stu-id="80df0-110">Patient</span></span>](#patient)
- [<span data-ttu-id="80df0-111">観察</span><span class="sxs-lookup"><span data-stu-id="80df0-111">Observation</span></span>](#observation)
- [<span data-ttu-id="80df0-112">状態</span><span class="sxs-lookup"><span data-stu-id="80df0-112">Condition</span></span>](#condition)
- [<span data-ttu-id="80df0-113">状況</span><span class="sxs-lookup"><span data-stu-id="80df0-113">Encounter</span></span>](#encounter)
- [<span data-ttu-id="80df0-114">Allergy Intolerance</span><span class="sxs-lookup"><span data-stu-id="80df0-114">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="80df0-115">サポート</span><span class="sxs-lookup"><span data-stu-id="80df0-115">Coverage</span></span>](#coverage)
- <span data-ttu-id="80df0-116">[投薬ステートメント](#medication-request) (PATIENTSAPP の DSTU2 バージョンの MedicationOrder を置き換えます)</span><span class="sxs-lookup"><span data-stu-id="80df0-116">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="80df0-117">場所 (このリソースから必要な情報は、発生する可能性があります)</span><span class="sxs-lookup"><span data-stu-id="80df0-117">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="80df0-118">患者のリソースは唯一の必須リソースです (アプリがまったく読み込まれなくなります)。ただし、Microsoft Teams の患者アプリを使用して、最も優れたエンドユーザーエクスペリエンスを実現するために、以下に記載されている仕様ごとに、上記のすべてのリソースのサポートを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="80df0-118">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="80df0-119">複数のリソースの Microsoft Teams の患者アプリからのクエリは、FHIR サーバーの URL に対する要求のバンドル (バッチ) を投稿するものとします。</span><span class="sxs-lookup"><span data-stu-id="80df0-119">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="80df0-120">サーバーは各要求を処理し、各要求によって一致したリソースのバンドルを返します。</span><span class="sxs-lookup"><span data-stu-id="80df0-120">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="80df0-121">詳細と例については、「」を参照してください [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="80df0-121">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="80df0-122">機能ステートメント</span><span class="sxs-lookup"><span data-stu-id="80df0-122">Capability Statement</span></span>

<span data-ttu-id="80df0-123">最低限必要なフィールドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="80df0-123">These are the minimum required fields:</span></span>

 - <span data-ttu-id="80df0-124">後</span><span class="sxs-lookup"><span data-stu-id="80df0-124">REST</span></span>

    - <span data-ttu-id="80df0-125">モード</span><span class="sxs-lookup"><span data-stu-id="80df0-125">Mode</span></span>
    - <span data-ttu-id="80df0-126">通信</span><span class="sxs-lookup"><span data-stu-id="80df0-126">Interaction</span></span>
    - <span data-ttu-id="80df0-127">リソース: 種類</span><span class="sxs-lookup"><span data-stu-id="80df0-127">Resource: Type</span></span>
    - <span data-ttu-id="80df0-128">セキュリティ: [OAuth uri 用の拡張子](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="80df0-128">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="80df0-129">FhirVersion (コードは、どのバージョンをピボットするかを理解するために必要です。)</span><span class="sxs-lookup"><span data-stu-id="80df0-129">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="80df0-130">[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80df0-130">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="80df0-131">診療</span><span class="sxs-lookup"><span data-stu-id="80df0-131">Patient</span></span>

<span data-ttu-id="80df0-132">以下は、Argonaut の患者プロファイルフィールドのサブセットである、必要な最小フィールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="80df0-132">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="80df0-133">名前。指定された</span><span class="sxs-lookup"><span data-stu-id="80df0-133">Name.Given</span></span>
 - <span data-ttu-id="80df0-134">家族</span><span class="sxs-lookup"><span data-stu-id="80df0-134">Name.Family</span></span>
 - <span data-ttu-id="80df0-135">女性</span><span class="sxs-lookup"><span data-stu-id="80df0-135">Gender</span></span>
 - <span data-ttu-id="80df0-136">地</span><span class="sxs-lookup"><span data-stu-id="80df0-136">BirthDate</span></span>
 - <span data-ttu-id="80df0-137">MRN (識別子)</span><span class="sxs-lookup"><span data-stu-id="80df0-137">MRN (Identifier)</span></span>

<span data-ttu-id="80df0-138">優れたユーザーエクスペリエンスを実現するために、 [Argonaut フィールド](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)に加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="80df0-138">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="80df0-139">名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="80df0-139">Name.Use</span></span>
 - <span data-ttu-id="80df0-140">名前プレフィックス</span><span class="sxs-lookup"><span data-stu-id="80df0-140">Name.Prefix</span></span>
 - <span data-ttu-id="80df0-141">[一般の専門スタッフ]-すべての専門スタッフ参照が患者リソースに含まれている必要があります (表示フィールドのみ)。</span><span class="sxs-lookup"><span data-stu-id="80df0-141">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="80df0-142">リソース検索では、/Patient/_search と次のパラメーターで POST メソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="80df0-142">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="80df0-143">id</span><span class="sxs-lookup"><span data-stu-id="80df0-143">id</span></span>
 - <span data-ttu-id="80df0-144">family = (ファミリ名に値が含まれているすべての患者を検索)</span><span class="sxs-lookup"><span data-stu-id="80df0-144">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="80df0-145">指定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="80df0-145">given=\<substring></span></span>
 - <span data-ttu-id="80df0-146">生年月日 = (完全一致)</span><span class="sxs-lookup"><span data-stu-id="80df0-146">birthdate=(exact match)</span></span>
 - <span data-ttu-id="80df0-147">性別 = (いずれかの管理者の性別の値)</span><span class="sxs-lookup"><span data-stu-id="80df0-147">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="80df0-148">\_count (返される結果の最大数)</span><span class="sxs-lookup"><span data-stu-id="80df0-148">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="80df0-149">応答には、 \_ 返されるレコードの数を制限するために、検索とカウントの結果として返されるレコードの合計数が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="80df0-149">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="80df0-150">識別子 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="80df0-150">identifier=\<mrn></span></span>

<span data-ttu-id="80df0-151">目標は、次のようにして患者の検索とフィルター処理を行うことができるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="80df0-151">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="80df0-152">ID: これは、FHIR のすべてのリソースが持つリソース ID です。</span><span class="sxs-lookup"><span data-stu-id="80df0-152">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="80df0-153">MRN: 診療員が知っている患者の実際の識別子です。</span><span class="sxs-lookup"><span data-stu-id="80df0-153">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="80df0-154">この MRN は、FHIR の識別子リソース内の識別子の種類に基づいています。</span><span class="sxs-lookup"><span data-stu-id="80df0-154">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="80df0-155">名前</span><span class="sxs-lookup"><span data-stu-id="80df0-155">Name</span></span>
- <span data-ttu-id="80df0-156">地</span><span class="sxs-lookup"><span data-stu-id="80df0-156">Birthdate</span></span>

<span data-ttu-id="80df0-157">次の通話の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80df0-157">See the following example of the call:</span></span>

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

<span data-ttu-id="80df0-158">[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80df0-158">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="80df0-159">観察</span><span class="sxs-lookup"><span data-stu-id="80df0-159">Observation</span></span>

<span data-ttu-id="80df0-160">これらは、 [Argonaut Vital-Signs プロファイル](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="80df0-160">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="80df0-161">発効 (日付と時刻)</span><span class="sxs-lookup"><span data-stu-id="80df0-161">Effective (date time or period)</span></span>
 - <span data-ttu-id="80df0-162">コードの記述</span><span class="sxs-lookup"><span data-stu-id="80df0-162">Code.Coding.Code</span></span>
 - <span data-ttu-id="80df0-163">Valu不定の値</span><span class="sxs-lookup"><span data-stu-id="80df0-163">ValueQuantity.Value</span></span>

<span data-ttu-id="80df0-164">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="80df0-164">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="80df0-165">コード。ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="80df0-165">Code.Coding.Display</span></span>
 - <span data-ttu-id="80df0-166">Valuの単位</span><span class="sxs-lookup"><span data-stu-id="80df0-166">ValueQuantity.Unit</span></span>

<span data-ttu-id="80df0-167">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="80df0-167">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="80df0-168">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="80df0-168">patient=\<patient id></span></span>
 - <span data-ttu-id="80df0-169">_sort =-date</span><span class="sxs-lookup"><span data-stu-id="80df0-169">_sort=-date</span></span>
 - <span data-ttu-id="80df0-170">category ("カテゴリ = バイタル-記号") を照会して、重要な記号の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="80df0-170">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="80df0-171">次の通話の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80df0-171">Refer to this example of the call:</span></span>

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

<span data-ttu-id="80df0-172">[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80df0-172">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="80df0-173">状態</span><span class="sxs-lookup"><span data-stu-id="80df0-173">Condition</span></span>

<span data-ttu-id="80df0-174">[Argonaut 条件プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)のサブセットである最小必須フィールドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="80df0-174">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="80df0-175">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="80df0-175">Code.Coding[0].Display</span></span>

<span data-ttu-id="80df0-176">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="80df0-176">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="80df0-177">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="80df0-177">AssertedDate</span></span>
 - <span data-ttu-id="80df0-178">程度</span><span class="sxs-lookup"><span data-stu-id="80df0-178">Severity</span></span>

<span data-ttu-id="80df0-179">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="80df0-179">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="80df0-180">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="80df0-180">patient=\<patient id></span></span>
 - <span data-ttu-id="80df0-181">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="80df0-181">_count=\<max results></span></span>

<span data-ttu-id="80df0-182">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80df0-182">See the following example of this call:</span></span>

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

<span data-ttu-id="80df0-183">[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80df0-183">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="80df0-184">状況</span><span class="sxs-lookup"><span data-stu-id="80df0-184">Encounter</span></span>

<span data-ttu-id="80df0-185">" [US Core](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) " というプロファイルのサブセットである最小必須フィールドは、"フィールドが含まれている必要があります" である必要があります。</span><span class="sxs-lookup"><span data-stu-id="80df0-185">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="80df0-186">状態</span><span class="sxs-lookup"><span data-stu-id="80df0-186">Status</span></span>
 - <span data-ttu-id="80df0-187">[0] と入力します。コーディング [0]。表示</span><span class="sxs-lookup"><span data-stu-id="80df0-187">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="80df0-188">さらに、US Core の次のフィールドは、プロファイルの "サポートが必要" フィールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="80df0-188">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="80df0-189">期間. 開始日</span><span class="sxs-lookup"><span data-stu-id="80df0-189">Period.Start</span></span>
 - <span data-ttu-id="80df0-190">場所 [0]場所。表示</span><span class="sxs-lookup"><span data-stu-id="80df0-190">Location[0].Location.Display</span></span>

<span data-ttu-id="80df0-191">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="80df0-191">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="80df0-192">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="80df0-192">patient=\<patient id></span></span>
 - <span data-ttu-id="80df0-193">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="80df0-193">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="80df0-194">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="80df0-194">_count=\<max results></span></span>

<span data-ttu-id="80df0-195">目標は、患者の最後の既知の場所を取得できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="80df0-195">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="80df0-196">各検出は、位置情報リソースを参照します。</span><span class="sxs-lookup"><span data-stu-id="80df0-196">Each encounter references a location resource.</span></span> <span data-ttu-id="80df0-197">参照には、場所の表示フィールドも含まれます。</span><span class="sxs-lookup"><span data-stu-id="80df0-197">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="80df0-198">[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80df0-198">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="80df0-199">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="80df0-199">AllergyIntolerance</span></span>

<span data-ttu-id="80df0-200">以下は、 [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="80df0-200">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="80df0-201">コード。テキスト</span><span class="sxs-lookup"><span data-stu-id="80df0-201">Code.Text</span></span>
 - <span data-ttu-id="80df0-202">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="80df0-202">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="80df0-203">ClinicalStatus/VerificationStatus (両方とも読む)</span><span class="sxs-lookup"><span data-stu-id="80df0-203">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="80df0-204">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリは次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="80df0-204">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="80df0-205">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="80df0-205">AssertedDate</span></span>
 - <span data-ttu-id="80df0-206">注テキスト</span><span class="sxs-lookup"><span data-stu-id="80df0-206">Note.Text</span></span>
 - <span data-ttu-id="80df0-207">反</span><span class="sxs-lookup"><span data-stu-id="80df0-207">Reaction</span></span>
    - <span data-ttu-id="80df0-208">物質 (1 つのコーディング要素)</span><span class="sxs-lookup"><span data-stu-id="80df0-208">Substance (one coding element)</span></span>
    - <span data-ttu-id="80df0-209">影響 (1 つのコード要素)</span><span class="sxs-lookup"><span data-stu-id="80df0-209">Manifestation (one coding element)</span></span>

<span data-ttu-id="80df0-210">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="80df0-210">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="80df0-211">患者 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="80df0-211">Patient =  \<patient id></span></span>

<span data-ttu-id="80df0-212">次の通話の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80df0-212">See the following example of the call:</span></span> 

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

<span data-ttu-id="80df0-213">[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80df0-213">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="80df0-214">投薬要求</span><span class="sxs-lookup"><span data-stu-id="80df0-214">Medication Request</span></span>

<span data-ttu-id="80df0-215">以下は、 [US Core 投薬要求プロファイル](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="80df0-215">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="80df0-216">投薬 (参照の場合)</span><span class="sxs-lookup"><span data-stu-id="80df0-216">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="80df0-217">投薬 (CodableConcept の場合)</span><span class="sxs-lookup"><span data-stu-id="80df0-217">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="80df0-218">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="80df0-218">AuthoredOn</span></span>
 - <span data-ttu-id="80df0-219">要求者。ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="80df0-219">Requester.Agent.Display</span></span>

<span data-ttu-id="80df0-220">優れたユーザーエクスペリエンスを実現するには、米国内のコアフィールドに加えて、患者のアプリでも次のフィールドを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="80df0-220">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="80df0-221">DosageInstruction [..]テキスト</span><span class="sxs-lookup"><span data-stu-id="80df0-221">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="80df0-222">テキスト</span><span class="sxs-lookup"><span data-stu-id="80df0-222">Text</span></span>

<span data-ttu-id="80df0-223">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="80df0-223">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="80df0-224">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="80df0-224">patient=\<patient id></span></span>
 - <span data-ttu-id="80df0-225">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="80df0-225">_count=\<max results></span></span>

<span data-ttu-id="80df0-226">[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80df0-226">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="80df0-227">サポート</span><span class="sxs-lookup"><span data-stu-id="80df0-227">Coverage</span></span>

<span data-ttu-id="80df0-228">以下は、US Core または Argonaut のプロファイルでカバーされていない最低限の必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="80df0-228">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="80df0-229">グループ化、少なくとも1つの要素を</span><span class="sxs-lookup"><span data-stu-id="80df0-229">Grouping, at least one element with</span></span>
    - <span data-ttu-id="80df0-230">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="80df0-230">GroupDisplay</span></span>
    - <span data-ttu-id="80df0-231">Plan ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="80df0-231">PlanDisplay</span></span>
 - <span data-ttu-id="80df0-232">ピリオド</span><span class="sxs-lookup"><span data-stu-id="80df0-232">Period</span></span>
 - <span data-ttu-id="80df0-233">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="80df0-233">SubscriberId</span></span>

<span data-ttu-id="80df0-234">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="80df0-234">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="80df0-235">患者 = \<patient id></span><span class="sxs-lookup"><span data-stu-id="80df0-235">Patient = \<patient id></span></span>

<span data-ttu-id="80df0-236">[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80df0-236">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
