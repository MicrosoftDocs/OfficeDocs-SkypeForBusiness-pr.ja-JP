---
title: 患者のアプリと EHR の統合 DSTU2 インターフェイス
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
description: Microsoft Teams の患者アプリと連携するように FHIR サーバーを設定または再構成するなど、Teams での DSTU2 インターフェイスの仕様について説明します。
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803485"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="6abeb-103">DSTU2 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="6abeb-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="6abeb-104">2020年10月30日の有効な患者アプリは廃止され、Teams の [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) で置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="6abeb-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="6abeb-105">患者のアプリデータは、チームをバックアップする Office 365 グループのグループメールボックスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6abeb-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="6abeb-106">患者アプリに関連付けられたデータはすべてこのグループに保持されますが、ユーザーインターフェイスからはアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="6abeb-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="6abeb-107">ユーザーは、 [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使ってリストを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="6abeb-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="6abeb-108">リストを使用すると、医療機関のケアチームは、ラウンドやさまざまなチーム会議から一般的な患者の監視までのシナリオのために患者リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6abeb-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="6abeb-109">始めるには、「患者」のテンプレートをリストから選びます。</span><span class="sxs-lookup"><span data-stu-id="6abeb-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="6abeb-110">組織でのリストアプリの管理方法の詳細については、「 [リストアプリを管理](../../manage-lists-app.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6abeb-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="6abeb-111">Microsoft Teams の患者と連携するように FHIR サーバーを設定または再構成するには、アプリがアクセスする必要があるデータを把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6abeb-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="6abeb-112">FHIR サーバーでは、次のリソースについて、バンドルを使った POST 要求をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6abeb-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="6abeb-113">診療</span><span class="sxs-lookup"><span data-stu-id="6abeb-113">Patient</span></span>](#patient)
- [<span data-ttu-id="6abeb-114">観察</span><span class="sxs-lookup"><span data-stu-id="6abeb-114">Observation</span></span>](#observation)
- [<span data-ttu-id="6abeb-115">状態</span><span class="sxs-lookup"><span data-stu-id="6abeb-115">Condition</span></span>](#condition)
- [<span data-ttu-id="6abeb-116">状況</span><span class="sxs-lookup"><span data-stu-id="6abeb-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="6abeb-117">Allergy intolerance</span><span class="sxs-lookup"><span data-stu-id="6abeb-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="6abeb-118">サポート</span><span class="sxs-lookup"><span data-stu-id="6abeb-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="6abeb-119">投薬注文</span><span class="sxs-lookup"><span data-stu-id="6abeb-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="6abeb-120">場所</span><span class="sxs-lookup"><span data-stu-id="6abeb-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="6abeb-121">患者リソースは唯一の必須リソースであり、アプリがまったく読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="6abeb-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="6abeb-122">ただし、Microsoft Teams の患者アプリを使用して、最も優れたエンドユーザーエクスペリエンスを実現するために、以下に記載されている仕様ごとに、上記のすべてのリソースのサポートを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6abeb-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="6abeb-123">Microsoft Teams の患者アプリから複数のリソースに対するクエリは、FHIR サーバーの URL への要求のバンドル (バッチ) を投稿します。</span><span class="sxs-lookup"><span data-stu-id="6abeb-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="6abeb-124">サーバーは各要求を処理し、各要求によって一致したリソースのバンドルを返します。</span><span class="sxs-lookup"><span data-stu-id="6abeb-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="6abeb-125">詳細と例については、「」を参照してください [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="6abeb-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="6abeb-126">以下のすべての FHIR リソースは、直接リソース参照によってアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6abeb-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="6abeb-127">準拠している必要な最小フィールドセット</span><span class="sxs-lookup"><span data-stu-id="6abeb-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="6abeb-128">FHIR サーバーでは、その機能の事実上の概要を把握するために、準拠のステートメントを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6abeb-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="6abeb-129">DSTU2 FHIR サーバーでは、次のパラメーターが想定されています。</span><span class="sxs-lookup"><span data-stu-id="6abeb-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="6abeb-130">後</span><span class="sxs-lookup"><span data-stu-id="6abeb-130">REST</span></span>

    - <span data-ttu-id="6abeb-131">モード</span><span class="sxs-lookup"><span data-stu-id="6abeb-131">Mode</span></span>
    - <span data-ttu-id="6abeb-132">通信</span><span class="sxs-lookup"><span data-stu-id="6abeb-132">Interaction</span></span>
    - <span data-ttu-id="6abeb-133">リソース: 種類</span><span class="sxs-lookup"><span data-stu-id="6abeb-133">Resource: Type</span></span>
    - <span data-ttu-id="6abeb-134">セキュリティ: [OAuth uri 用の拡張子](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="6abeb-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="6abeb-135">FhirVersion (Microsoft のコードでは、複数のバージョンをサポートするために、どのバージョンをピボットする必要があるかを理解する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="6abeb-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="6abeb-136">[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6abeb-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="6abeb-137">診療</span><span class="sxs-lookup"><span data-stu-id="6abeb-137">Patient</span></span>

<span data-ttu-id="6abeb-138">以下は、 [Argonaut の患者プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) フィールドのサブセットである、最小の必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="6abeb-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="6abeb-139">家族</span><span class="sxs-lookup"><span data-stu-id="6abeb-139">Name.Family</span></span>
 - <span data-ttu-id="6abeb-140">名前。指定された</span><span class="sxs-lookup"><span data-stu-id="6abeb-140">Name.Given</span></span>
 - <span data-ttu-id="6abeb-141">女性</span><span class="sxs-lookup"><span data-stu-id="6abeb-141">Gender</span></span>
 - <span data-ttu-id="6abeb-142">地</span><span class="sxs-lookup"><span data-stu-id="6abeb-142">BirthDate</span></span>
 - <span data-ttu-id="6abeb-143">MRN (識別子)</span><span class="sxs-lookup"><span data-stu-id="6abeb-143">MRN (Identifier)</span></span>

<span data-ttu-id="6abeb-144">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリも次のフィールドを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="6abeb-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="6abeb-145">名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6abeb-145">Name.Use</span></span>
 - <span data-ttu-id="6abeb-146">名前プレフィックス</span><span class="sxs-lookup"><span data-stu-id="6abeb-146">Name.Prefix</span></span>
 - <span data-ttu-id="6abeb-147">CareProvider (患者リソースのこの参照には、次の例に示す表示フィールドを含める必要があります)。</span><span class="sxs-lookup"><span data-stu-id="6abeb-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

    ```
    Request:
    GET <fhir-server>/Patient/<patient-id>
    
    Response:
    {
      "resourceType": "Patient",
      "id": "<patient-id>",
      .
      .
      .
      "name": [
        {
          "use": "official",
          "prefix": [ "Mr" ],
          "family": [ "Chau" ],
          "given": [ "Hugh" ]
        }
      ],
      "identifier": [
        {
          "use": "official",
          "type": {
            "coding": [
              {
                "system": "https://hl7.org/fhir/v2/0203",
                "code": "MR"
              }
            ]
          },
          "value": "1234567"
        }
      ],
      "gender": "male",
      "birthDate": "1957-06-05",
      "careProvider": [{ "display": "Jane Doe" }],
    }
    ```

<span data-ttu-id="6abeb-148">リソース検索では、/Patient/_search と次のパラメーターで POST メソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="6abeb-148">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="6abeb-149">id</span><span class="sxs-lookup"><span data-stu-id="6abeb-149">id</span></span>
 - <span data-ttu-id="6abeb-150">ファミリ: contains = (ファミリ名に値が含まれているすべての患者を検索します。)</span><span class="sxs-lookup"><span data-stu-id="6abeb-150">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="6abeb-151">指定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="6abeb-151">given=\<substring></span></span>
 - <span data-ttu-id="6abeb-152">name =\<substring></span><span class="sxs-lookup"><span data-stu-id="6abeb-152">name=\<substring></span></span>
 - <span data-ttu-id="6abeb-153">生年月日 = (完全一致)</span><span class="sxs-lookup"><span data-stu-id="6abeb-153">birthdate=(exact match)</span></span>
 - <span data-ttu-id="6abeb-154">\_count (返される結果の最大数)</span><span class="sxs-lookup"><span data-stu-id="6abeb-154">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="6abeb-155">応答には、検索結果として返されるレコードの合計数が含まれている必要があり \_ ます。カウントは、返されるレコードの数を制限するために PatientsApp によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="6abeb-155">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="6abeb-156">識別子 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="6abeb-156">identifier=\<mrn></span></span>

<span data-ttu-id="6abeb-157">目標は、次のようにして患者の検索とフィルター処理を行うことができるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="6abeb-157">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="6abeb-158">ID: これは、FHIR のすべてのリソースが持つリソース ID です。</span><span class="sxs-lookup"><span data-stu-id="6abeb-158">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="6abeb-159">MRN: 診療員が知っている患者の実際の識別子です。</span><span class="sxs-lookup"><span data-stu-id="6abeb-159">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="6abeb-160">この MRN は、FHIR の識別子リソース内の識別子の種類に基づいていることを理解しています。</span><span class="sxs-lookup"><span data-stu-id="6abeb-160">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="6abeb-161">名前</span><span class="sxs-lookup"><span data-stu-id="6abeb-161">Name</span></span>
- <span data-ttu-id="6abeb-162">地</span><span class="sxs-lookup"><span data-stu-id="6abeb-162">Birthdate</span></span>

<span data-ttu-id="6abeb-163">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6abeb-163">See the following example  of this call.</span></span>

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=hugh&family=chau

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  .
  .
  .
  "entry": [
    {
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "name": [
          {
            "text": "Hugh Chau",
            "family": [ "Chau" ],
            "given": [ "Hugh" ]
          }
        ],
        "gender": "male",
        "birthDate": "1957-06-05"
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

<span data-ttu-id="6abeb-164">[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6abeb-164">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="6abeb-165">観察</span><span class="sxs-lookup"><span data-stu-id="6abeb-165">Observation</span></span>

<span data-ttu-id="6abeb-166">以下は、必須の最小フィールドであり、Argonaut の重要な署名プロファイルのサブセットです。</span><span class="sxs-lookup"><span data-stu-id="6abeb-166">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="6abeb-167">発効 (日付と時刻)</span><span class="sxs-lookup"><span data-stu-id="6abeb-167">Effective (date time or period)</span></span>
 - <span data-ttu-id="6abeb-168">コードの記述</span><span class="sxs-lookup"><span data-stu-id="6abeb-168">Code.Coding.Code</span></span>
 - <span data-ttu-id="6abeb-169">Valu不定の値</span><span class="sxs-lookup"><span data-stu-id="6abeb-169">ValueQuantity.Value</span></span>

<span data-ttu-id="6abeb-170">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリも次のフィールドを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="6abeb-170">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="6abeb-171">コード。ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="6abeb-171">Code.Coding.Display</span></span>
 - <span data-ttu-id="6abeb-172">Valuの単位</span><span class="sxs-lookup"><span data-stu-id="6abeb-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="6abeb-173">コンポーネントの所見を使う場合は、各コンポーネントの観測に同じロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="6abeb-173">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="6abeb-174">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="6abeb-174">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="6abeb-175">患者 =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="6abeb-175">patient=\<patient id\></span></span>
 - <span data-ttu-id="6abeb-176">sort: desc =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="6abeb-176">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="6abeb-177">目標は、患者の最新のバイタル・サインを取得できるようにすることです (観測された VitalSigns)。</span><span class="sxs-lookup"><span data-stu-id="6abeb-177">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs

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
        "category": {
          "coding": [ { code": "vital-signs" } ],
        },
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "39156-5",
              "display": "bmi"
            }
          ],
        },
        "effectiveDateTime": "2009-12-01",
        "valueQuantity": {
          "value": 34.4,
          "unit": "kg/m2",
          "system": "http://unitsofmeasure.org",
          "code": "kg/m2"
        }
      },
    },
    .
    .
    .
  ]
}
```

<span data-ttu-id="6abeb-178">[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6abeb-178">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="6abeb-179">状態</span><span class="sxs-lookup"><span data-stu-id="6abeb-179">Condition</span></span>

<span data-ttu-id="6abeb-180">以下は、 [Argonaut 条件プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)の一部である最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="6abeb-180">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="6abeb-181">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="6abeb-181">Code.Coding[0].Display</span></span>

<span data-ttu-id="6abeb-182">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="6abeb-182">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="6abeb-183">記録された日付</span><span class="sxs-lookup"><span data-stu-id="6abeb-183">Date Recorded</span></span>
 - <span data-ttu-id="6abeb-184">程度</span><span class="sxs-lookup"><span data-stu-id="6abeb-184">Severity</span></span>

<span data-ttu-id="6abeb-185">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="6abeb-185">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="6abeb-186">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="6abeb-186">patient=\<patient id></span></span>
 - <span data-ttu-id="6abeb-187">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="6abeb-187">_count=\<max results></span></span>

<span data-ttu-id="6abeb-188">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6abeb-188">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "386033004",
              "display": "Neuropathy (nerve damage)"
            }
          ]
        },
        "dateRecorded": "2018-09-17",
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        }
      },
    }
  ]
}
```

<span data-ttu-id="6abeb-189">[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6abeb-189">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="6abeb-190">状況</span><span class="sxs-lookup"><span data-stu-id="6abeb-190">Encounter</span></span>

<span data-ttu-id="6abeb-191">"US Core" というプロファイルのサブセットである、最低限必要なフィールドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6abeb-191">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="6abeb-192">状態</span><span class="sxs-lookup"><span data-stu-id="6abeb-192">Status</span></span>
 - <span data-ttu-id="6abeb-193">[0] と入力します。コーディング [0]。表示</span><span class="sxs-lookup"><span data-stu-id="6abeb-193">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="6abeb-194">さらに、US Core の次のフィールドは、プロファイルの "サポートが必要" フィールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="6abeb-194">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="6abeb-195">期間. 開始日</span><span class="sxs-lookup"><span data-stu-id="6abeb-195">Period.Start</span></span>
 - <span data-ttu-id="6abeb-196">場所 [0]場所。表示</span><span class="sxs-lookup"><span data-stu-id="6abeb-196">Location[0].Location.Display</span></span>

<span data-ttu-id="6abeb-197">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="6abeb-197">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="6abeb-198">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="6abeb-198">patient=\<patient id></span></span>
 - <span data-ttu-id="6abeb-199">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="6abeb-199">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="6abeb-200">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="6abeb-200">_count=\<max results></span></span>

<span data-ttu-id="6abeb-201">目標は、患者の最後の既知の場所を取得できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="6abeb-201">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="6abeb-202">各検出は、位置情報リソースを参照します。</span><span class="sxs-lookup"><span data-stu-id="6abeb-202">Each encounter references a location resource.</span></span> <span data-ttu-id="6abeb-203">参照には、場所の表示フィールドも含まれます。</span><span class="sxs-lookup"><span data-stu-id="6abeb-203">The reference shall also include the location's display field.</span></span> <span data-ttu-id="6abeb-204">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6abeb-204">See the following example of this call.</span></span>

```
Request:
GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Encounter",
        "id": "<resource-id>",
        "identifier": [{ "use": "official", "value": "<id>" }],
        "status": "arrived",
        "type": [
          {
            "coding": [{ "display": "Appointment" }],
          }
        ],
        "patient": { "reference": "Patient/<patient-id>" },
        "period": { "start": "09/17/2018 1:00:00 PM" },
        "location": [
          {
            "location": { "display": "Clinic - ENT" },
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="6abeb-205">[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6abeb-205">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="6abeb-206">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="6abeb-206">AllergyIntolerance</span></span>

<span data-ttu-id="6abeb-207">以下は、Argonaut AllergyIntolerance profile のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="6abeb-207">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="6abeb-208">コード。テキスト</span><span class="sxs-lookup"><span data-stu-id="6abeb-208">Code.Text</span></span>
 - <span data-ttu-id="6abeb-209">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="6abeb-209">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="6abeb-210">状態</span><span class="sxs-lookup"><span data-stu-id="6abeb-210">Status</span></span>

<span data-ttu-id="6abeb-211">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリも次のフィールドを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="6abeb-211">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="6abeb-212">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="6abeb-212">RecordedDate</span></span>
 - <span data-ttu-id="6abeb-213">注テキスト</span><span class="sxs-lookup"><span data-stu-id="6abeb-213">Note.Text</span></span>
 - <span data-ttu-id="6abeb-214">反力 [..]物質。テキスト</span><span class="sxs-lookup"><span data-stu-id="6abeb-214">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="6abeb-215">反力 [..]影響 [..]テキスト</span><span class="sxs-lookup"><span data-stu-id="6abeb-215">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="6abeb-216">テキストの Div</span><span class="sxs-lookup"><span data-stu-id="6abeb-216">Text.Div</span></span>

<span data-ttu-id="6abeb-217">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="6abeb-217">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="6abeb-218">患者 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="6abeb-218">Patient =  \<patient id></span></span>

<span data-ttu-id="6abeb-219">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6abeb-219">See the following example of this call:</span></span>

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
        "recordedDate": "2018-09-17T07:00:00.000Z",
        "substance": {
          "text": "Cashew nuts"
        },
        "status": "confirmed",
        "reaction": [
          {
            "substance": {
              "text": "cashew nut allergenic extract Injectable Product"
            },
            "manifestation": [
              {
                "text": "Anaphylactic reaction"
              }
            ]
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="6abeb-220">[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6abeb-220">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="6abeb-221">投薬注文</span><span class="sxs-lookup"><span data-stu-id="6abeb-221">Medication Order</span></span>

<span data-ttu-id="6abeb-222">以下は、Argonaut MedicationOrder profile のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="6abeb-222">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="6abeb-223">記録された日付</span><span class="sxs-lookup"><span data-stu-id="6abeb-223">DateWritten</span></span>
 - <span data-ttu-id="6abeb-224">Prescriber</span><span class="sxs-lookup"><span data-stu-id="6abeb-224">Prescriber.Display</span></span>
 - <span data-ttu-id="6abeb-225">投薬 (参照の場合)</span><span class="sxs-lookup"><span data-stu-id="6abeb-225">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="6abeb-226">投薬 (概念の場合)</span><span class="sxs-lookup"><span data-stu-id="6abeb-226">Medication.Text (if concept)</span></span>

<span data-ttu-id="6abeb-227">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="6abeb-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="6abeb-228">DateEnded</span><span class="sxs-lookup"><span data-stu-id="6abeb-228">DateEnded</span></span>
 - <span data-ttu-id="6abeb-229">DosageInstruction。</span><span class="sxs-lookup"><span data-stu-id="6abeb-229">DosageInstruction.Text</span></span>
 - <span data-ttu-id="6abeb-230">テキストの Div</span><span class="sxs-lookup"><span data-stu-id="6abeb-230">Text.Div</span></span>

<span data-ttu-id="6abeb-231">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="6abeb-231">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="6abeb-232">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="6abeb-232">patient=\<patient id></span></span>
 - <span data-ttu-id="6abeb-233">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="6abeb-233">_count=\<max results></span></span>

<span data-ttu-id="6abeb-234">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6abeb-234">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "MedicationOrder",
        "id": "<resource-id>",
        "dateWritten": "2018-09-17",
        "medicationCodeableConcept": {
          "text": "Lisinopril 20 MG Oral Tablet"
        },
        "prescriber": {
          "display": "Jane Doe"
        },
        "dosageInstruction": [
          {
            "text": "1 daily"
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="6abeb-235">[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6abeb-235">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="6abeb-236">サポート</span><span class="sxs-lookup"><span data-stu-id="6abeb-236">Coverage</span></span>

<span data-ttu-id="6abeb-237">以下は、US Core または Argonaut のプロファイルでカバーされていない最低限の必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="6abeb-237">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="6abeb-238">給料または</span><span class="sxs-lookup"><span data-stu-id="6abeb-238">Payor</span></span>

<span data-ttu-id="6abeb-239">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="6abeb-239">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="6abeb-240">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="6abeb-240">patient=\<patient id></span></span>

<span data-ttu-id="6abeb-241">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6abeb-241">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/Coverage?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Coverage",
        "id": "<resource-id>",
        "plan": "No Primary Insurance",
        "subscriber": { "reference": "Patient/<patient-id>" }
      }
    }
  ]
}
```
    
<span data-ttu-id="6abeb-242">[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6abeb-242">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="6abeb-243">場所</span><span class="sxs-lookup"><span data-stu-id="6abeb-243">Location</span></span>

<span data-ttu-id="6abeb-244">このリソース [は、リソースの参照](#encounter) としてのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="6abeb-244">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="6abeb-245">[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6abeb-245">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
