---
title: Patients App and EHR integration DSTU2 interface
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
description: Teams で DSTU2 インターフェイスの仕様について説明します。Microsoft Teams Patients アプリで動作する FHIR サーバーの設定や再構成などです。
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803485"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="6346f-103">DSTU2 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="6346f-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="6346f-104">2020 年 10 月 30 日より、患者アプリは廃止され、Teams の[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="6346f-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="6346f-105">患者アプリのデータは、チームを支援する Office 365 グループのグループ メールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="6346f-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="6346f-106">患者アプリに関連付けられているすべてのデータはこのグループに保持されますが、ユーザー インターフェイスからアクセスすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="6346f-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="6346f-107">ユーザーは、[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使用してリストを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="6346f-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="6346f-108">リストを使用すると、医療機関のケア チームは、ラウンドや学際的なチーム会議から一般的な患者の監視に至るまでのシナリオで患者リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6346f-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="6346f-109">開始するには、リストの患者テンプレートを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6346f-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="6346f-110">組織でリスト アプリを管理する方法の詳細については、「[リスト アプリの管理](../../manage-lists-app.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6346f-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="6346f-111">Microsoft Teams Patients アプリで動作する FHIR サーバーを設定または再構成するには、アプリがアクセスする必要があるデータを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6346f-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="6346f-112">FHIR サーバーは、次のリソースのバンドルを使用した POST 要求をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6346f-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="6346f-113">患者</span><span class="sxs-lookup"><span data-stu-id="6346f-113">Patient</span></span>](#patient)
- [<span data-ttu-id="6346f-114">観察</span><span class="sxs-lookup"><span data-stu-id="6346f-114">Observation</span></span>](#observation)
- [<span data-ttu-id="6346f-115">状態</span><span class="sxs-lookup"><span data-stu-id="6346f-115">Condition</span></span>](#condition)
- [<span data-ttu-id="6346f-116">Encounter</span><span class="sxs-lookup"><span data-stu-id="6346f-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="6346f-117">取り込み中の容容性</span><span class="sxs-lookup"><span data-stu-id="6346f-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="6346f-118">対象範囲</span><span class="sxs-lookup"><span data-stu-id="6346f-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="6346f-119">薬の順序</span><span class="sxs-lookup"><span data-stu-id="6346f-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="6346f-120">場所</span><span class="sxs-lookup"><span data-stu-id="6346f-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="6346f-121">Patient リソースは唯一の必須リソースです (アプリが読み込めずに)。</span><span class="sxs-lookup"><span data-stu-id="6346f-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="6346f-122">ただし、パートナーは、以下に示す仕様に従って上記のすべてのリソースのサポートを実装し、Microsoft Teams Patients アプリを使用した最適なエクスペリエンスを実現Microsoft Teams勧めします。</span><span class="sxs-lookup"><span data-stu-id="6346f-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="6346f-123">FHIR サーバー Microsoft Teams要求のバンドル (BATCH) 後に複数のリソースについて、Microsoft Teams Patients アプリからクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="6346f-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="6346f-124">サーバーは各要求を処理し、各要求に一致するリソースのバンドルを返します。</span><span class="sxs-lookup"><span data-stu-id="6346f-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="6346f-125">詳細と例については、 を参照してください [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="6346f-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="6346f-126">次のすべての FHIR リソースには、直接リソース参照でアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6346f-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="6346f-127">準拠の最小必須フィールド セット</span><span class="sxs-lookup"><span data-stu-id="6346f-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="6346f-128">FHIR Server は、機能の概要を実際に説明するために、準拠ステートメントを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6346f-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="6346f-129">DSTU2 FHIR サーバーでは、次のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="6346f-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="6346f-130">REST</span><span class="sxs-lookup"><span data-stu-id="6346f-130">REST</span></span>

    - <span data-ttu-id="6346f-131">モード</span><span class="sxs-lookup"><span data-stu-id="6346f-131">Mode</span></span>
    - <span data-ttu-id="6346f-132">対話</span><span class="sxs-lookup"><span data-stu-id="6346f-132">Interaction</span></span>
    - <span data-ttu-id="6346f-133">リソース: 型</span><span class="sxs-lookup"><span data-stu-id="6346f-133">Resource: Type</span></span>
    - <span data-ttu-id="6346f-134">セキュリティ: [OAuth URI の拡張機能](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="6346f-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="6346f-135">FhirVersion (複数のバージョンをサポートする場合、どのバージョンにピボットする必要があるのか理解するには、このコードが必要です)。</span><span class="sxs-lookup"><span data-stu-id="6346f-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="6346f-136">この [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) フィールド セットのその他の詳細については、 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6346f-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="6346f-137">患者</span><span class="sxs-lookup"><span data-stu-id="6346f-137">Patient</span></span>

<span data-ttu-id="6346f-138">これらは [、Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) 患者プロファイル フィールドのサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="6346f-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="6346f-139">Name.Family</span><span class="sxs-lookup"><span data-stu-id="6346f-139">Name.Family</span></span>
 - <span data-ttu-id="6346f-140">Name.Given</span><span class="sxs-lookup"><span data-stu-id="6346f-140">Name.Given</span></span>
 - <span data-ttu-id="6346f-141">性別</span><span class="sxs-lookup"><span data-stu-id="6346f-141">Gender</span></span>
 - <span data-ttu-id="6346f-142">BirthDate</span><span class="sxs-lookup"><span data-stu-id="6346f-142">BirthDate</span></span>
 - <span data-ttu-id="6346f-143">MRN (識別子)</span><span class="sxs-lookup"><span data-stu-id="6346f-143">MRN (Identifier)</span></span>

<span data-ttu-id="6346f-144">Argonaut フィールドに加えて、ユーザー エクスペリエンスを向上するために、Patients アプリでは次のフィールドも読み上げられます。</span><span class="sxs-lookup"><span data-stu-id="6346f-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="6346f-145">Name.Use</span><span class="sxs-lookup"><span data-stu-id="6346f-145">Name.Use</span></span>
 - <span data-ttu-id="6346f-146">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="6346f-146">Name.Prefix</span></span>
 - <span data-ttu-id="6346f-147">CareProvider (Patient リソースのこの参照には、次の例に示す表示フィールドを含める必要があります)。</span><span class="sxs-lookup"><span data-stu-id="6346f-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="6346f-148">リソース検索では、/Patient/_search の POST メソッドと次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6346f-148">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="6346f-149">id</span><span class="sxs-lookup"><span data-stu-id="6346f-149">id</span></span>
 - <span data-ttu-id="6346f-150">family:contains=(家族名に値が含まれているすべての患者を検索します)。</span><span class="sxs-lookup"><span data-stu-id="6346f-150">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="6346f-151">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="6346f-151">given=\<substring></span></span>
 - <span data-ttu-id="6346f-152">name=\<substring></span><span class="sxs-lookup"><span data-stu-id="6346f-152">name=\<substring></span></span>
 - <span data-ttu-id="6346f-153">birthdate=(完全一致)</span><span class="sxs-lookup"><span data-stu-id="6346f-153">birthdate=(exact match)</span></span>
 - <span data-ttu-id="6346f-154">\_count (返される結果の最大数)</span><span class="sxs-lookup"><span data-stu-id="6346f-154">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="6346f-155">応答には、検索の結果として返されたレコードの総数を含める必要があります。Count は、PatientsApp によって返されるレコードの数を制限するために \_ 使用されます。</span><span class="sxs-lookup"><span data-stu-id="6346f-155">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="6346f-156">identifier=\<mrn></span><span class="sxs-lookup"><span data-stu-id="6346f-156">identifier=\<mrn></span></span>

<span data-ttu-id="6346f-157">目標は、次の方法で患者を検索してフィルター処理できる状態に設定します。</span><span class="sxs-lookup"><span data-stu-id="6346f-157">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="6346f-158">ID: これは、FHIR のすべてのリソースが持つリソース ID です。</span><span class="sxs-lookup"><span data-stu-id="6346f-158">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="6346f-159">MRN: これは、医療スタッフが知る患者の実際の識別子です。</span><span class="sxs-lookup"><span data-stu-id="6346f-159">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="6346f-160">この MRN は、FHIR の識別子リソース内の識別子の種類に基づくと理解しています</span><span class="sxs-lookup"><span data-stu-id="6346f-160">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="6346f-161">名前</span><span class="sxs-lookup"><span data-stu-id="6346f-161">Name</span></span>
- <span data-ttu-id="6346f-162">生年月日</span><span class="sxs-lookup"><span data-stu-id="6346f-162">Birthdate</span></span>

<span data-ttu-id="6346f-163">この呼び出しの次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6346f-163">See the following example  of this call.</span></span>

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

<span data-ttu-id="6346f-164">この [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) フィールド セットのその他の詳細については、 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6346f-164">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="6346f-165">観察</span><span class="sxs-lookup"><span data-stu-id="6346f-165">Observation</span></span>

<span data-ttu-id="6346f-166">これらは、Argonaut バイタサイン プロファイルのサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="6346f-166">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="6346f-167">有効 (日付の時刻または期間)</span><span class="sxs-lookup"><span data-stu-id="6346f-167">Effective (date time or period)</span></span>
 - <span data-ttu-id="6346f-168">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="6346f-168">Code.Coding.Code</span></span>
 - <span data-ttu-id="6346f-169">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="6346f-169">ValueQuantity.Value</span></span>

<span data-ttu-id="6346f-170">Argonaut フィールドに加えて、ユーザー エクスペリエンスを向上するために、Patients アプリでは次のフィールドも読み上げられます。</span><span class="sxs-lookup"><span data-stu-id="6346f-170">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="6346f-171">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="6346f-171">Code.Coding.Display</span></span>
 - <span data-ttu-id="6346f-172">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="6346f-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="6346f-173">コンポーネントの観察を使用する場合は、各コンポーネントの観察に同じロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="6346f-173">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="6346f-174">リソース検索では、GET メソッドと次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6346f-174">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="6346f-175">patient=\<patient id\></span><span class="sxs-lookup"><span data-stu-id="6346f-175">patient=\<patient id\></span></span>
 - <span data-ttu-id="6346f-176">sort:desc=\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="6346f-176">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="6346f-177">目標は、患者の最新の重要な兆候 [VitalSigns.DSTU.saz] (観察?) を取得できる点です。</span><span class="sxs-lookup"><span data-stu-id="6346f-177">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="6346f-178">この [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) フィールド セットのその他の詳細については、 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6346f-178">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="6346f-179">状態</span><span class="sxs-lookup"><span data-stu-id="6346f-179">Condition</span></span>

<span data-ttu-id="6346f-180">これらは、Argonaut 条件プロファイルのサブセットである最小 [必須フィールドです](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)。</span><span class="sxs-lookup"><span data-stu-id="6346f-180">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="6346f-181">Code.Coding[0].表示</span><span class="sxs-lookup"><span data-stu-id="6346f-181">Code.Coding[0].Display</span></span>

<span data-ttu-id="6346f-182">Argonaut フィールドに加えて、ユーザー エクスペリエンスを向上するために、Patients アプリは次のフィールドも読み取り可能です。</span><span class="sxs-lookup"><span data-stu-id="6346f-182">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="6346f-183">記録日</span><span class="sxs-lookup"><span data-stu-id="6346f-183">Date Recorded</span></span>
 - <span data-ttu-id="6346f-184">重大度</span><span class="sxs-lookup"><span data-stu-id="6346f-184">Severity</span></span>

<span data-ttu-id="6346f-185">リソース検索では、GET メソッドと次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6346f-185">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="6346f-186">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="6346f-186">patient=\<patient id></span></span>
 - <span data-ttu-id="6346f-187">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="6346f-187">_count=\<max results></span></span>

<span data-ttu-id="6346f-188">この呼び出しの次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6346f-188">See the following example of this call:</span></span>

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

<span data-ttu-id="6346f-189">この [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) フィールド セットのその他の詳細については、 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6346f-189">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="6346f-190">Encounter</span><span class="sxs-lookup"><span data-stu-id="6346f-190">Encounter</span></span>

<span data-ttu-id="6346f-191">これらは、US Core Encounter プロファイルの "must have" フィールドのサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="6346f-191">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="6346f-192">状態</span><span class="sxs-lookup"><span data-stu-id="6346f-192">Status</span></span>
 - <span data-ttu-id="6346f-193">「[0]」と入力します。Coding[0].表示</span><span class="sxs-lookup"><span data-stu-id="6346f-193">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="6346f-194">さらに、US Core Encounter プロファイルの "サポートが必要" フィールドの次のフィールド</span><span class="sxs-lookup"><span data-stu-id="6346f-194">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="6346f-195">Period.Start</span><span class="sxs-lookup"><span data-stu-id="6346f-195">Period.Start</span></span>
 - <span data-ttu-id="6346f-196">Location[0].Location.Display</span><span class="sxs-lookup"><span data-stu-id="6346f-196">Location[0].Location.Display</span></span>

<span data-ttu-id="6346f-197">リソース検索では、GET メソッドと次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6346f-197">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="6346f-198">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="6346f-198">patient=\<patient id></span></span>
 - <span data-ttu-id="6346f-199">_sort:desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="6346f-199">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="6346f-200">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="6346f-200">_count=\<max results></span></span>

<span data-ttu-id="6346f-201">目標は、患者の最後の既知の場所を取得できる点です。</span><span class="sxs-lookup"><span data-stu-id="6346f-201">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="6346f-202">各エンカウンターは、場所リソースを参照します。</span><span class="sxs-lookup"><span data-stu-id="6346f-202">Each encounter references a location resource.</span></span> <span data-ttu-id="6346f-203">参照には、場所の表示フィールドも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6346f-203">The reference shall also include the location's display field.</span></span> <span data-ttu-id="6346f-204">この呼び出しの次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6346f-204">See the following example of this call.</span></span>

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

<span data-ttu-id="6346f-205">この [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) フィールド セットのその他の詳細については、 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6346f-205">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="6346f-206">分性Intolerance</span><span class="sxs-lookup"><span data-stu-id="6346f-206">AllergyIntolerance</span></span>

<span data-ttu-id="6346f-207">次に示すのは必須の最小フィールドです。これは、Argonautいしなやかプロファイルのサブセットです。</span><span class="sxs-lookup"><span data-stu-id="6346f-207">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="6346f-208">Code.Text</span><span class="sxs-lookup"><span data-stu-id="6346f-208">Code.Text</span></span>
 - <span data-ttu-id="6346f-209">Code.Coding[0].表示</span><span class="sxs-lookup"><span data-stu-id="6346f-209">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="6346f-210">状態</span><span class="sxs-lookup"><span data-stu-id="6346f-210">Status</span></span>

<span data-ttu-id="6346f-211">Argonaut フィールドに加えて、ユーザー エクスペリエンスを向上するために、Patients アプリでは次のフィールドも読み上げられます。</span><span class="sxs-lookup"><span data-stu-id="6346f-211">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="6346f-212">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="6346f-212">RecordedDate</span></span>
 - <span data-ttu-id="6346f-213">Note.Text</span><span class="sxs-lookup"><span data-stu-id="6346f-213">Note.Text</span></span>
 - <span data-ttu-id="6346f-214">Reaction[..].Substance.Text</span><span class="sxs-lookup"><span data-stu-id="6346f-214">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="6346f-215">Reaction[..].[..].テキスト</span><span class="sxs-lookup"><span data-stu-id="6346f-215">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="6346f-216">Text.Div</span><span class="sxs-lookup"><span data-stu-id="6346f-216">Text.Div</span></span>

<span data-ttu-id="6346f-217">リソース検索では、GET メソッドと次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6346f-217">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="6346f-218">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="6346f-218">Patient =  \<patient id></span></span>

<span data-ttu-id="6346f-219">この呼び出しの次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6346f-219">See the following example of this call:</span></span>

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

<span data-ttu-id="6346f-220">この [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) フィールド セットのその他の詳細については、 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6346f-220">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="6346f-221">薬の順序</span><span class="sxs-lookup"><span data-stu-id="6346f-221">Medication Order</span></span>

<span data-ttu-id="6346f-222">これらは、ArgonautOrder プロファイルのサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="6346f-222">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="6346f-223">DateWritten</span><span class="sxs-lookup"><span data-stu-id="6346f-223">DateWritten</span></span>
 - <span data-ttu-id="6346f-224">Prescriber.Display</span><span class="sxs-lookup"><span data-stu-id="6346f-224">Prescriber.Display</span></span>
 - <span data-ttu-id="6346f-225">しだい.Display (参考資料の場合)</span><span class="sxs-lookup"><span data-stu-id="6346f-225">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="6346f-226">しだい.Text (概念の場合)</span><span class="sxs-lookup"><span data-stu-id="6346f-226">Medication.Text (if concept)</span></span>

<span data-ttu-id="6346f-227">Argonaut フィールドに加えて、ユーザー エクスペリエンスを向上するために、Patients アプリは次のフィールドも読み取り可能です。</span><span class="sxs-lookup"><span data-stu-id="6346f-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="6346f-228">DateEnded</span><span class="sxs-lookup"><span data-stu-id="6346f-228">DateEnded</span></span>
 - <span data-ttu-id="6346f-229">ストラクター.Text</span><span class="sxs-lookup"><span data-stu-id="6346f-229">DosageInstruction.Text</span></span>
 - <span data-ttu-id="6346f-230">Text.Div</span><span class="sxs-lookup"><span data-stu-id="6346f-230">Text.Div</span></span>

<span data-ttu-id="6346f-231">リソース検索では、GET メソッドと次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6346f-231">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="6346f-232">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="6346f-232">patient=\<patient id></span></span>
 - <span data-ttu-id="6346f-233">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="6346f-233">_count=\<max results></span></span>

<span data-ttu-id="6346f-234">この呼び出しの次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6346f-234">See the following example of this call:</span></span>

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

<span data-ttu-id="6346f-235">この [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) フィールド セットのその他の詳細については、 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6346f-235">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="6346f-236">対象範囲</span><span class="sxs-lookup"><span data-stu-id="6346f-236">Coverage</span></span>

<span data-ttu-id="6346f-237">これらは必須の最小フィールドで、US Core プロファイルまたは Argonaut プロファイルの対象外です。</span><span class="sxs-lookup"><span data-stu-id="6346f-237">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="6346f-238">Payor</span><span class="sxs-lookup"><span data-stu-id="6346f-238">Payor</span></span>

<span data-ttu-id="6346f-239">リソース検索では、GET メソッドと次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6346f-239">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="6346f-240">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="6346f-240">patient=\<patient id></span></span>

<span data-ttu-id="6346f-241">この呼び出しの次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6346f-241">See the following example of this call:</span></span>

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
    
<span data-ttu-id="6346f-242">この [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) フィールド セットのその他の詳細については、 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6346f-242">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="6346f-243">場所</span><span class="sxs-lookup"><span data-stu-id="6346f-243">Location</span></span>

<span data-ttu-id="6346f-244">このリソースは、Encounter リソースの参照として [のみ使用](#encounter) されます。</span><span class="sxs-lookup"><span data-stu-id="6346f-244">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="6346f-245">この [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) フィールド セットのその他の詳細については、 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6346f-245">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
