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
ms.openlocfilehash: 15bcc5fcaff50d6d41c45ef2d38e34719ebca999
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772208"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="0736f-103">DSTU2 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="0736f-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="0736f-104">2020年10月30日の有効な患者アプリは廃止され、Teams の [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) で置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="0736f-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="0736f-105">リストを使用すると、医療機関のケアチームは、ラウンドやさまざまなチーム会議から一般的な患者の監視までのシナリオのために患者リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0736f-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="0736f-106">始めるには、「患者」のテンプレートをリストから選びます。</span><span class="sxs-lookup"><span data-stu-id="0736f-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="0736f-107">組織でのリストアプリの管理方法の詳細については、「[リストアプリを管理](../../manage-lists-app.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0736f-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md)</span></span>

<span data-ttu-id="0736f-108">Microsoft Teams の患者と連携するように FHIR サーバーを設定または再構成するには、アプリがアクセスする必要があるデータを把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0736f-108">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="0736f-109">FHIR サーバーでは、次のリソースについて、バンドルを使った POST 要求をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0736f-109">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="0736f-110">診療</span><span class="sxs-lookup"><span data-stu-id="0736f-110">Patient</span></span>](#patient)
- [<span data-ttu-id="0736f-111">観察</span><span class="sxs-lookup"><span data-stu-id="0736f-111">Observation</span></span>](#observation)
- [<span data-ttu-id="0736f-112">状態</span><span class="sxs-lookup"><span data-stu-id="0736f-112">Condition</span></span>](#condition)
- [<span data-ttu-id="0736f-113">状況</span><span class="sxs-lookup"><span data-stu-id="0736f-113">Encounter</span></span>](#encounter)
- [<span data-ttu-id="0736f-114">Allergy intolerance</span><span class="sxs-lookup"><span data-stu-id="0736f-114">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="0736f-115">サポート</span><span class="sxs-lookup"><span data-stu-id="0736f-115">Coverage</span></span>](#coverage)
- [<span data-ttu-id="0736f-116">投薬注文</span><span class="sxs-lookup"><span data-stu-id="0736f-116">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="0736f-117">場所</span><span class="sxs-lookup"><span data-stu-id="0736f-117">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="0736f-118">患者リソースは唯一の必須リソースであり、アプリがまったく読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="0736f-118">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="0736f-119">ただし、Microsoft Teams の患者アプリを使用して、最も優れたエンドユーザーエクスペリエンスを実現するために、以下に記載されている仕様ごとに、上記のすべてのリソースのサポートを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0736f-119">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="0736f-120">Microsoft Teams の患者アプリから複数のリソースに対するクエリは、FHIR サーバーの URL への要求のバンドル (バッチ) を投稿します。</span><span class="sxs-lookup"><span data-stu-id="0736f-120">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="0736f-121">サーバーは各要求を処理し、各要求によって一致したリソースのバンドルを返します。</span><span class="sxs-lookup"><span data-stu-id="0736f-121">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="0736f-122">詳細と例については、「」を参照してください [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="0736f-122">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="0736f-123">以下のすべての FHIR リソースは、直接リソース参照によってアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0736f-123">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="0736f-124">準拠している必要な最小フィールドセット</span><span class="sxs-lookup"><span data-stu-id="0736f-124">Conformance minimum required field set</span></span>

 <span data-ttu-id="0736f-125">FHIR サーバーでは、その機能の事実上の概要を把握するために、準拠のステートメントを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0736f-125">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="0736f-126">DSTU2 FHIR サーバーでは、次のパラメーターが想定されています。</span><span class="sxs-lookup"><span data-stu-id="0736f-126">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="0736f-127">後</span><span class="sxs-lookup"><span data-stu-id="0736f-127">REST</span></span>

    - <span data-ttu-id="0736f-128">モード</span><span class="sxs-lookup"><span data-stu-id="0736f-128">Mode</span></span>
    - <span data-ttu-id="0736f-129">通信</span><span class="sxs-lookup"><span data-stu-id="0736f-129">Interaction</span></span>
    - <span data-ttu-id="0736f-130">リソース: 種類</span><span class="sxs-lookup"><span data-stu-id="0736f-130">Resource: Type</span></span>
    - <span data-ttu-id="0736f-131">セキュリティ: [OAuth uri 用の拡張子](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="0736f-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="0736f-132">FhirVersion (Microsoft のコードでは、複数のバージョンをサポートするために、どのバージョンをピボットする必要があるかを理解する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="0736f-132">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="0736f-133">[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0736f-133">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="0736f-134">診療</span><span class="sxs-lookup"><span data-stu-id="0736f-134">Patient</span></span>

<span data-ttu-id="0736f-135">以下は、 [Argonaut の患者プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) フィールドのサブセットである、最小の必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="0736f-135">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="0736f-136">家族</span><span class="sxs-lookup"><span data-stu-id="0736f-136">Name.Family</span></span>
 - <span data-ttu-id="0736f-137">名前。指定された</span><span class="sxs-lookup"><span data-stu-id="0736f-137">Name.Given</span></span>
 - <span data-ttu-id="0736f-138">女性</span><span class="sxs-lookup"><span data-stu-id="0736f-138">Gender</span></span>
 - <span data-ttu-id="0736f-139">地</span><span class="sxs-lookup"><span data-stu-id="0736f-139">BirthDate</span></span>
 - <span data-ttu-id="0736f-140">MRN (識別子)</span><span class="sxs-lookup"><span data-stu-id="0736f-140">MRN (Identifier)</span></span>

<span data-ttu-id="0736f-141">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリも次のフィールドを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="0736f-141">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="0736f-142">名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0736f-142">Name.Use</span></span>
 - <span data-ttu-id="0736f-143">名前プレフィックス</span><span class="sxs-lookup"><span data-stu-id="0736f-143">Name.Prefix</span></span>
 - <span data-ttu-id="0736f-144">CareProvider (患者リソースのこの参照には、次の例に示す表示フィールドを含める必要があります)。</span><span class="sxs-lookup"><span data-stu-id="0736f-144">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="0736f-145">リソース検索では、/Patient/_search と次のパラメーターで POST メソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="0736f-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="0736f-146">id</span><span class="sxs-lookup"><span data-stu-id="0736f-146">id</span></span>
 - <span data-ttu-id="0736f-147">ファミリ: contains = (ファミリ名に値が含まれているすべての患者を検索します。)</span><span class="sxs-lookup"><span data-stu-id="0736f-147">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="0736f-148">指定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="0736f-148">given=\<substring></span></span>
 - <span data-ttu-id="0736f-149">name =\<substring></span><span class="sxs-lookup"><span data-stu-id="0736f-149">name=\<substring></span></span>
 - <span data-ttu-id="0736f-150">生年月日 = (完全一致)</span><span class="sxs-lookup"><span data-stu-id="0736f-150">birthdate=(exact match)</span></span>
 - <span data-ttu-id="0736f-151">\_count (返される結果の最大数)</span><span class="sxs-lookup"><span data-stu-id="0736f-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="0736f-152">応答には、検索結果として返されるレコードの合計数が含まれている必要があり \_ ます。カウントは、返されるレコードの数を制限するために PatientsApp によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="0736f-152">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="0736f-153">識別子 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="0736f-153">identifier=\<mrn></span></span>

<span data-ttu-id="0736f-154">目標は、次のようにして患者の検索とフィルター処理を行うことができるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="0736f-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="0736f-155">ID: これは、FHIR のすべてのリソースが持つリソース ID です。</span><span class="sxs-lookup"><span data-stu-id="0736f-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="0736f-156">MRN: 診療員が知っている患者の実際の識別子です。</span><span class="sxs-lookup"><span data-stu-id="0736f-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="0736f-157">この MRN は、FHIR の識別子リソース内の識別子の種類に基づいていることを理解しています。</span><span class="sxs-lookup"><span data-stu-id="0736f-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="0736f-158">名前</span><span class="sxs-lookup"><span data-stu-id="0736f-158">Name</span></span>
- <span data-ttu-id="0736f-159">地</span><span class="sxs-lookup"><span data-stu-id="0736f-159">Birthdate</span></span>

<span data-ttu-id="0736f-160">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0736f-160">See the following example  of this call.</span></span>

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

<span data-ttu-id="0736f-161">[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0736f-161">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="0736f-162">観察</span><span class="sxs-lookup"><span data-stu-id="0736f-162">Observation</span></span>

<span data-ttu-id="0736f-163">以下は、必須の最小フィールドであり、Argonaut の重要な署名プロファイルのサブセットです。</span><span class="sxs-lookup"><span data-stu-id="0736f-163">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="0736f-164">発効 (日付と時刻)</span><span class="sxs-lookup"><span data-stu-id="0736f-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="0736f-165">コードの記述</span><span class="sxs-lookup"><span data-stu-id="0736f-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="0736f-166">Valu不定の値</span><span class="sxs-lookup"><span data-stu-id="0736f-166">ValueQuantity.Value</span></span>

<span data-ttu-id="0736f-167">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリも次のフィールドを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="0736f-167">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="0736f-168">コード。ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="0736f-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="0736f-169">Valuの単位</span><span class="sxs-lookup"><span data-stu-id="0736f-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="0736f-170">コンポーネントの所見を使う場合は、各コンポーネントの観測に同じロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="0736f-170">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="0736f-171">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="0736f-171">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="0736f-172">患者 =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="0736f-172">patient=\<patient id\></span></span>
 - <span data-ttu-id="0736f-173">sort: desc =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="0736f-173">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="0736f-174">目標は、患者の最新のバイタル・サインを取得できるようにすることです (観測された VitalSigns)。</span><span class="sxs-lookup"><span data-stu-id="0736f-174">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="0736f-175">[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0736f-175">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="0736f-176">状態</span><span class="sxs-lookup"><span data-stu-id="0736f-176">Condition</span></span>

<span data-ttu-id="0736f-177">以下は、 [Argonaut 条件プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)の一部である最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="0736f-177">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="0736f-178">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="0736f-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="0736f-179">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="0736f-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="0736f-180">記録された日付</span><span class="sxs-lookup"><span data-stu-id="0736f-180">Date Recorded</span></span>
 - <span data-ttu-id="0736f-181">程度</span><span class="sxs-lookup"><span data-stu-id="0736f-181">Severity</span></span>

<span data-ttu-id="0736f-182">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="0736f-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="0736f-183">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="0736f-183">patient=\<patient id></span></span>
 - <span data-ttu-id="0736f-184">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="0736f-184">_count=\<max results></span></span>

<span data-ttu-id="0736f-185">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0736f-185">See the following example of this call:</span></span>

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

<span data-ttu-id="0736f-186">[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0736f-186">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="0736f-187">状況</span><span class="sxs-lookup"><span data-stu-id="0736f-187">Encounter</span></span>

<span data-ttu-id="0736f-188">"US Core" というプロファイルのサブセットである、最低限必要なフィールドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0736f-188">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="0736f-189">状態</span><span class="sxs-lookup"><span data-stu-id="0736f-189">Status</span></span>
 - <span data-ttu-id="0736f-190">[0] と入力します。コーディング [0]。表示</span><span class="sxs-lookup"><span data-stu-id="0736f-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="0736f-191">さらに、US Core の次のフィールドは、プロファイルの "サポートが必要" フィールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="0736f-191">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="0736f-192">期間. 開始日</span><span class="sxs-lookup"><span data-stu-id="0736f-192">Period.Start</span></span>
 - <span data-ttu-id="0736f-193">場所 [0]場所。表示</span><span class="sxs-lookup"><span data-stu-id="0736f-193">Location[0].Location.Display</span></span>

<span data-ttu-id="0736f-194">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="0736f-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="0736f-195">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="0736f-195">patient=\<patient id></span></span>
 - <span data-ttu-id="0736f-196">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="0736f-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="0736f-197">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="0736f-197">_count=\<max results></span></span>

<span data-ttu-id="0736f-198">目標は、患者の最後の既知の場所を取得できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="0736f-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="0736f-199">各検出は、位置情報リソースを参照します。</span><span class="sxs-lookup"><span data-stu-id="0736f-199">Each encounter references a location resource.</span></span> <span data-ttu-id="0736f-200">参照には、場所の表示フィールドも含まれます。</span><span class="sxs-lookup"><span data-stu-id="0736f-200">The reference shall also include the location's display field.</span></span> <span data-ttu-id="0736f-201">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0736f-201">See the following example of this call.</span></span>

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

<span data-ttu-id="0736f-202">[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0736f-202">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="0736f-203">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="0736f-203">AllergyIntolerance</span></span>

<span data-ttu-id="0736f-204">以下は、Argonaut AllergyIntolerance profile のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="0736f-204">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="0736f-205">コード。テキスト</span><span class="sxs-lookup"><span data-stu-id="0736f-205">Code.Text</span></span>
 - <span data-ttu-id="0736f-206">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="0736f-206">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="0736f-207">状態</span><span class="sxs-lookup"><span data-stu-id="0736f-207">Status</span></span>

<span data-ttu-id="0736f-208">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリも次のフィールドを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="0736f-208">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="0736f-209">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="0736f-209">RecordedDate</span></span>
 - <span data-ttu-id="0736f-210">注テキスト</span><span class="sxs-lookup"><span data-stu-id="0736f-210">Note.Text</span></span>
 - <span data-ttu-id="0736f-211">反力 [..]物質。テキスト</span><span class="sxs-lookup"><span data-stu-id="0736f-211">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="0736f-212">反力 [..]影響 [..]テキスト</span><span class="sxs-lookup"><span data-stu-id="0736f-212">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="0736f-213">テキストの Div</span><span class="sxs-lookup"><span data-stu-id="0736f-213">Text.Div</span></span>

<span data-ttu-id="0736f-214">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="0736f-214">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="0736f-215">患者 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="0736f-215">Patient =  \<patient id></span></span>

<span data-ttu-id="0736f-216">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0736f-216">See the following example of this call:</span></span>

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

<span data-ttu-id="0736f-217">[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0736f-217">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="0736f-218">投薬注文</span><span class="sxs-lookup"><span data-stu-id="0736f-218">Medication Order</span></span>

<span data-ttu-id="0736f-219">以下は、Argonaut MedicationOrder profile のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="0736f-219">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="0736f-220">記録された日付</span><span class="sxs-lookup"><span data-stu-id="0736f-220">DateWritten</span></span>
 - <span data-ttu-id="0736f-221">Prescriber</span><span class="sxs-lookup"><span data-stu-id="0736f-221">Prescriber.Display</span></span>
 - <span data-ttu-id="0736f-222">投薬 (参照の場合)</span><span class="sxs-lookup"><span data-stu-id="0736f-222">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="0736f-223">投薬 (概念の場合)</span><span class="sxs-lookup"><span data-stu-id="0736f-223">Medication.Text (if concept)</span></span>

<span data-ttu-id="0736f-224">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="0736f-224">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="0736f-225">DateEnded</span><span class="sxs-lookup"><span data-stu-id="0736f-225">DateEnded</span></span>
 - <span data-ttu-id="0736f-226">DosageInstruction。</span><span class="sxs-lookup"><span data-stu-id="0736f-226">DosageInstruction.Text</span></span>
 - <span data-ttu-id="0736f-227">テキストの Div</span><span class="sxs-lookup"><span data-stu-id="0736f-227">Text.Div</span></span>

<span data-ttu-id="0736f-228">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="0736f-228">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="0736f-229">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="0736f-229">patient=\<patient id></span></span>
 - <span data-ttu-id="0736f-230">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="0736f-230">_count=\<max results></span></span>

<span data-ttu-id="0736f-231">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0736f-231">See the following example of this call:</span></span>

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

<span data-ttu-id="0736f-232">[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0736f-232">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="0736f-233">サポート</span><span class="sxs-lookup"><span data-stu-id="0736f-233">Coverage</span></span>

<span data-ttu-id="0736f-234">以下は、US Core または Argonaut のプロファイルでカバーされていない最低限の必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="0736f-234">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="0736f-235">給料または</span><span class="sxs-lookup"><span data-stu-id="0736f-235">Payor</span></span>

<span data-ttu-id="0736f-236">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="0736f-236">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="0736f-237">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="0736f-237">patient=\<patient id></span></span>

<span data-ttu-id="0736f-238">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0736f-238">See the following example of this call:</span></span>

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
    
<span data-ttu-id="0736f-239">[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0736f-239">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="0736f-240">場所</span><span class="sxs-lookup"><span data-stu-id="0736f-240">Location</span></span>

<span data-ttu-id="0736f-241">このリソース [は、リソースの参照](#encounter) としてのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="0736f-241">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="0736f-242">[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0736f-242">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
