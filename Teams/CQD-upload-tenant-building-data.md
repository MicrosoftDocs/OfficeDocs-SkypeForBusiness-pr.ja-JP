---
title: 通話品質ダッシュボード (CQD) でテナントと建物のデータをアップロードする
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 通話品質ダッシュボード (CQD) でテナントと建物のデータをアップロードする方法について学習します。
ms.openlocfilehash: a7f8b4a8d84429b752692cf05013dfba7321fd5e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909351"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a><span data-ttu-id="83e99-103">通話品質ダッシュボード (CQD) でテナントと建物のデータをアップロードする</span><span class="sxs-lookup"><span data-stu-id="83e99-103">Upload tenant and building data in Call Quality Dashboard (CQD)</span></span>


<span data-ttu-id="83e99-104">通話品質ダッシュボード (CQD) を利用するには、テナントをアップロードしてデータを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="83e99-104">To get the most out of Call Quality Dashboard (CQD), we recommend that you upload your tenant and building data.</span></span> <span data-ttu-id="83e99-105">テナント データ ファイルには、建物とエンドポイントの 2[種類](#upload-building-data-file)[があります](#endpoint-data-file)。</span><span class="sxs-lookup"><span data-stu-id="83e99-105">There are 2 types of tenant data files, [Building](#upload-building-data-file) and [Endpoint](#endpoint-data-file).</span></span>

<span data-ttu-id="83e99-106">ここでサンプル テナント データ テンプレートをダウンロード [できます](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="83e99-106">You can download a sample tenant data template [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).</span></span> <span data-ttu-id="83e99-107">マッピングの作成に関するヘルプについては [、「CQD の建物マップを作成する」を参照してください](CQD-building-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="83e99-107">For help with building mapping, read [Create a building map for CQD](CQD-building-mapping.md).</span></span>

<span data-ttu-id="83e99-108">CQD サマリー レポート ダッシュボードで、[CQD 設定] メニュー  (CQD の上部にある歯車アイコン) から [テナント データのアップロード] を選択します。 </span><span class="sxs-lookup"><span data-stu-id="83e99-108">From the CQD Summary Reports dashboard, select **Tenant Data Upload** from the CQD **Settings** menu (a gear icon at the top of CQD).</span></span> <span data-ttu-id="83e99-109">管理者はここから、IP アドレスと地理的情報のマッピング、各ワイヤレス アクセス ポイントとその MAC アドレスのマッピングなど、組織の建物とエンドポイントの情報をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="83e99-109">From here, admins can upload their organization's building and endpoint information, such as mapping of IP addresses and geographical information, mapping each wireless access point and its MAC address, etc.</span></span>

1. <span data-ttu-id="83e99-110">CQD (Teams 管理センターまたは At) を開き、右上隅の歯車アイコンを選択し、[概要レポート] ページから [テナント データのアップロード] を [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) **選択** します。 </span><span class="sxs-lookup"><span data-stu-id="83e99-110">Open CQD (from the Teams admin center, or at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)), then select the gear icon in the upper-right corner and choose **Tenant Data Upload** from the **Summary Reports** page.</span></span>

   ![データのアップロード中に表示されるダイアログ ボックスのスクリーンショット](media/qerguide-image-tenantdataupload.png)
    
2. <span data-ttu-id="83e99-112">また、CQD を初めて訪問する場合は、建物のデータをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-112">Alternatively, if this is your first time visiting CQD, you'll be asked to upload building data.</span></span> <span data-ttu-id="83e99-113">[今すぐ **アップロード] を選** び、[テナント データのアップロード] ページ **にすばやく移動** できます。</span><span class="sxs-lookup"><span data-stu-id="83e99-113">You can select **Upload Now** to quickly navigate to the **Tenant Data Upload** page.</span></span>

   ![建物のデータをアップロードするユーザーに通知するバナーのスクリーンショット](media/qerguide-image-buildingdatauploadbanner.png)

3. <span data-ttu-id="83e99-115">[テナント データ **のアップロード] ページで** 、[参照] を **選択** してデータ ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="83e99-115">On the **Tenant Data Upload** page, select **Browse** to choose a data file.</span></span>

4. <span data-ttu-id="83e99-116">データ ファイルを選び、[開始日] を **指定** し、必要に応じて終了日を指定します。</span><span class="sxs-lookup"><span data-stu-id="83e99-116">After selecting a data file, specify **Start date** and, optionally, specify an end date.</span></span>

5. <span data-ttu-id="83e99-117">[開始日]**を選択した後、[\*\*\*\*アップロード]** を選択して CQD にファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="83e99-117">After selecting **Start date**, select **Upload** to upload the file to CQD.</span></span> <br><br><span data-ttu-id="83e99-118">ファイルがアップロードされる前に、検証されます。</span><span class="sxs-lookup"><span data-stu-id="83e99-118">Before the file is uploaded, it's validated.</span></span> <span data-ttu-id="83e99-119">検証に失敗すると、ファイルの修正を要求するエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="83e99-119">If validation fails, an error message is displayed requesting that you correct the file.</span></span> <span data-ttu-id="83e99-120">次の図は、データ ファイルの列数が正しくない場合に発生するエラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="83e99-120">The following figure shows an error occurring when the number of columns in the data file is incorrect.</span></span>

   ![建物データのアップロード エラーを表示するダイアログ ボックスの例](media/qerguide-image-buildingdatauploaderror.png)
 
6. <span data-ttu-id="83e99-122">検証中にエラーが発生しない場合、ファイルのアップロードは成功します。</span><span class="sxs-lookup"><span data-stu-id="83e99-122">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="83e99-123">アップロードしたデータ ファイルは、[マイ アップロード] テーブルに表示されます。このテーブルには、そのページの下部にある現在のテナントでアップロードされたファイルの完全な一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="83e99-123">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>

> [!NOTE]
> <span data-ttu-id="83e99-124">建物ファイルの処理が完了するために最大 4 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-124">It can take up to four hours to finish processing the building file.</span></span> <br><br> <span data-ttu-id="83e99-125">既に建物ファイルをアップロード済みで、見逃しているか除外されている可能性があるサブネットを追加する必要がある場合は、新しいサブネットを追加して元のファイルを変更し、現在のファイルを削除し、新しく編集したファイルを再アップロードします。</span><span class="sxs-lookup"><span data-stu-id="83e99-125">If you've already uploaded a building file and need to add subnets that might have been missed or excluded, modify the original file by adding the new subnets, remove the current file, and re-upload the newly edited file.</span></span> <span data-ttu-id="83e99-126">CQD に作成できるアクティブな建物データ ファイルは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="83e99-126">There can be only one active building data file in CQD.</span></span> 


## <a name="upload-building-data-file"></a><span data-ttu-id="83e99-127">建物データ ファイルをアップロードする</span><span class="sxs-lookup"><span data-stu-id="83e99-127">Upload building data file</span></span>

<span data-ttu-id="83e99-128">CQD のテナント データ ファイルの最初の種類は、 **建物データ** ファイルです。</span><span class="sxs-lookup"><span data-stu-id="83e99-128">The first type of tenant data file in CQD is the **Building** data file.</span></span> <span data-ttu-id="83e99-129">サブネット列は、Network+ NetworkRange 列を展開し、そのサブネット列を通話レコードの最初のサブネット列または第 2 のサブネット列に結合して、建物、市区町ビル、国、または地域の情報を表示することで導き出されます。</span><span class="sxs-lookup"><span data-stu-id="83e99-129">The Subnet column is derived by expanding the Network+NetworkRange column, then joining the Subnet column to the call record’s First Subnet or Second Subnet column to show Building, City, Country, or Region information.</span></span> <span data-ttu-id="83e99-130">アップロードするデータ ファイルの形式は、アップロード前に検証チェックに合格するには、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-130">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>
  
- <span data-ttu-id="83e99-131">ファイルは .tsv ファイル (列はタブで区切られています) または .csv ファイル (列はコンマで区切られています) のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-131">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="83e99-132">データ ファイルには、テーブルの見出し行は含されません。</span><span class="sxs-lookup"><span data-stu-id="83e99-132">The data file doesn't include a table header row.</span></span> <span data-ttu-id="83e99-133">データ ファイルの最初の行は、"ネットワーク" のようなヘッダー ラベルではなく、実際のデータである必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-133">The first line of the data file is expected to be real data, not header labels like "Network".</span></span>

- <span data-ttu-id="83e99-134">ファイル内のデータ型には、文字列、整数、またはブール値のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="83e99-134">Data types in the file can only be String, Integer, or Boolean.</span></span> <span data-ttu-id="83e99-135">整数データ型の場合、値は数値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-135">For the  Integer data type, the value must be a numeric value.</span></span> <span data-ttu-id="83e99-136">ブール値は 0 または 1 のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-136">Boolean values must be either 0 or 1.</span></span>

- <span data-ttu-id="83e99-137">列で文字列データ型を使用する場合、データ フィールドは空白でも、タブまたはコンマで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-137">If a column uses the String data type, a data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="83e99-138">空のデータ フィールドには、空の文字列値が割り当て込まれます。</span><span class="sxs-lookup"><span data-stu-id="83e99-138">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="83e99-139">各行には 15 列が必要です。各列には適切なデータ型が必要です。列は次の表に示す順序である必要があります (コンマまたはタブ区切り)。</span><span class="sxs-lookup"><span data-stu-id="83e99-139">There must be 15 columns for each row, each column must have the appropriate data type, and the columns must be in the order listed in the following table (comma or tab delimited):</span></span>

  <span data-ttu-id="83e99-140">**データ ファイル形式を構築する**</span><span class="sxs-lookup"><span data-stu-id="83e99-140">**Building data file format**</span></span>
  
  | <span data-ttu-id="83e99-141">列名</span><span class="sxs-lookup"><span data-stu-id="83e99-141">Column name</span></span>        | <span data-ttu-id="83e99-142">データ型</span><span class="sxs-lookup"><span data-stu-id="83e99-142">Data type</span></span> | <span data-ttu-id="83e99-143">例</span><span class="sxs-lookup"><span data-stu-id="83e99-143">Example</span></span>                   | <span data-ttu-id="83e99-144">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="83e99-144">Guidance</span></span>              |
  |--------------------|-----------|---------------------------|-----------------------|
  | <span data-ttu-id="83e99-145">NetworkIP</span><span class="sxs-lookup"><span data-stu-id="83e99-145">NetworkIP</span></span>          | <span data-ttu-id="83e99-146">文字列</span><span class="sxs-lookup"><span data-stu-id="83e99-146">String</span></span>    | <span data-ttu-id="83e99-147">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="83e99-147">192.168.1.0</span></span>               | <span data-ttu-id="83e99-148">必須</span><span class="sxs-lookup"><span data-stu-id="83e99-148">Required</span></span>              |
  | <span data-ttu-id="83e99-149">NetworkName</span><span class="sxs-lookup"><span data-stu-id="83e99-149">NetworkName</span></span>        | <span data-ttu-id="83e99-150">文字列</span><span class="sxs-lookup"><span data-stu-id="83e99-150">String</span></span>    | <span data-ttu-id="83e99-151">USA/Seattle/SEATTLE-SEA-1</span><span class="sxs-lookup"><span data-stu-id="83e99-151">USA/Seattle/SEATTLE-SEA-1</span></span> | <span data-ttu-id="83e99-152">必須<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="83e99-152">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="83e99-153">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="83e99-153">NetworkRange</span></span>       | <span data-ttu-id="83e99-154">数値</span><span class="sxs-lookup"><span data-stu-id="83e99-154">Number</span></span>    | <span data-ttu-id="83e99-155">26</span><span class="sxs-lookup"><span data-stu-id="83e99-155">26</span></span>                        | <span data-ttu-id="83e99-156">必須</span><span class="sxs-lookup"><span data-stu-id="83e99-156">Required</span></span>              |
  | <span data-ttu-id="83e99-157">BuildingName</span><span class="sxs-lookup"><span data-stu-id="83e99-157">BuildingName</span></span>       | <span data-ttu-id="83e99-158">文字列</span><span class="sxs-lookup"><span data-stu-id="83e99-158">String</span></span>    | <span data-ttu-id="83e99-159">SEATTLE-SEA-1</span><span class="sxs-lookup"><span data-stu-id="83e99-159">SEATTLE-SEA-1</span></span>             | <span data-ttu-id="83e99-160">必須<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="83e99-160">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="83e99-161">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="83e99-161">OwnershipType</span></span>      | <span data-ttu-id="83e99-162">文字列</span><span class="sxs-lookup"><span data-stu-id="83e99-162">String</span></span>    | <span data-ttu-id="83e99-163">Contoso</span><span class="sxs-lookup"><span data-stu-id="83e99-163">Contoso</span></span>                   | <span data-ttu-id="83e99-164">省略可能</span><span class="sxs-lookup"><span data-stu-id="83e99-164">Optional</span></span>              |
  | <span data-ttu-id="83e99-165">BuildingType</span><span class="sxs-lookup"><span data-stu-id="83e99-165">BuildingType</span></span>       | <span data-ttu-id="83e99-166">文字列</span><span class="sxs-lookup"><span data-stu-id="83e99-166">String</span></span>    | <span data-ttu-id="83e99-167">IT 終了</span><span class="sxs-lookup"><span data-stu-id="83e99-167">IT Termination</span></span>            | <span data-ttu-id="83e99-168">省略可能</span><span class="sxs-lookup"><span data-stu-id="83e99-168">Optional</span></span>              |
  | <span data-ttu-id="83e99-169">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="83e99-169">BuildingOfficeType</span></span> | <span data-ttu-id="83e99-170">文字列</span><span class="sxs-lookup"><span data-stu-id="83e99-170">String</span></span>    | <span data-ttu-id="83e99-171">エンジニアリング</span><span class="sxs-lookup"><span data-stu-id="83e99-171">Engineering</span></span>               | <span data-ttu-id="83e99-172">省略可能</span><span class="sxs-lookup"><span data-stu-id="83e99-172">Optional</span></span>              |
  | <span data-ttu-id="83e99-173">市区町村</span><span class="sxs-lookup"><span data-stu-id="83e99-173">City</span></span>               | <span data-ttu-id="83e99-174">文字列</span><span class="sxs-lookup"><span data-stu-id="83e99-174">String</span></span>    | <span data-ttu-id="83e99-175">調布市調布ヶ丘</span><span class="sxs-lookup"><span data-stu-id="83e99-175">Seattle</span></span>                   | <span data-ttu-id="83e99-176">推奨</span><span class="sxs-lookup"><span data-stu-id="83e99-176">Recommended</span></span>           |
  | <span data-ttu-id="83e99-177">ZipCode</span><span class="sxs-lookup"><span data-stu-id="83e99-177">ZipCode</span></span>            | <span data-ttu-id="83e99-178">文字列</span><span class="sxs-lookup"><span data-stu-id="83e99-178">String</span></span>    | <span data-ttu-id="83e99-179">98001</span><span class="sxs-lookup"><span data-stu-id="83e99-179">98001</span></span>                     | <span data-ttu-id="83e99-180">推奨</span><span class="sxs-lookup"><span data-stu-id="83e99-180">Recommended</span></span>           |
  | <span data-ttu-id="83e99-181">国</span><span class="sxs-lookup"><span data-stu-id="83e99-181">Country</span></span>            | <span data-ttu-id="83e99-182">文字列</span><span class="sxs-lookup"><span data-stu-id="83e99-182">String</span></span>    | <span data-ttu-id="83e99-183">米国</span><span class="sxs-lookup"><span data-stu-id="83e99-183">US</span></span>                        | <span data-ttu-id="83e99-184">推奨</span><span class="sxs-lookup"><span data-stu-id="83e99-184">Recommended</span></span>           |
  | <span data-ttu-id="83e99-185">都道府県</span><span class="sxs-lookup"><span data-stu-id="83e99-185">State</span></span>              | <span data-ttu-id="83e99-186">文字列</span><span class="sxs-lookup"><span data-stu-id="83e99-186">String</span></span>    | <span data-ttu-id="83e99-187">WA</span><span class="sxs-lookup"><span data-stu-id="83e99-187">WA</span></span>                        | <span data-ttu-id="83e99-188">推奨</span><span class="sxs-lookup"><span data-stu-id="83e99-188">Recommended</span></span>           |
  | <span data-ttu-id="83e99-189">Region</span><span class="sxs-lookup"><span data-stu-id="83e99-189">Region</span></span>             | <span data-ttu-id="83e99-190">文字列</span><span class="sxs-lookup"><span data-stu-id="83e99-190">String</span></span>    | <span data-ttu-id="83e99-191">MSUS</span><span class="sxs-lookup"><span data-stu-id="83e99-191">MSUS</span></span>                      | <span data-ttu-id="83e99-192">推奨</span><span class="sxs-lookup"><span data-stu-id="83e99-192">Recommended</span></span>           |
  | <span data-ttu-id="83e99-193">InsideCorp<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="83e99-193">InsideCorp<sup>2</sup></span></span>         | <span data-ttu-id="83e99-194">ブール</span><span class="sxs-lookup"><span data-stu-id="83e99-194">Bool</span></span>      | <span data-ttu-id="83e99-195">1</span><span class="sxs-lookup"><span data-stu-id="83e99-195">1</span></span>             | <span data-ttu-id="83e99-196">必須</span><span class="sxs-lookup"><span data-stu-id="83e99-196">Required</span></span>              |
  | <span data-ttu-id="83e99-197">ExpressRoute<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="83e99-197">ExpressRoute<sup>3</sup></span></span>       | <span data-ttu-id="83e99-198">ブール</span><span class="sxs-lookup"><span data-stu-id="83e99-198">Bool</span></span>      | <span data-ttu-id="83e99-199">0</span><span class="sxs-lookup"><span data-stu-id="83e99-199">0</span></span>             | <span data-ttu-id="83e99-200">必須</span><span class="sxs-lookup"><span data-stu-id="83e99-200">Required</span></span>              |
  | <span data-ttu-id="83e99-201">VPN</span><span class="sxs-lookup"><span data-stu-id="83e99-201">VPN</span></span>                | <span data-ttu-id="83e99-202">ブール</span><span class="sxs-lookup"><span data-stu-id="83e99-202">Bool</span></span>      | <span data-ttu-id="83e99-203">0</span><span class="sxs-lookup"><span data-stu-id="83e99-203">0</span></span>                         | <span data-ttu-id="83e99-204">省略可能</span><span class="sxs-lookup"><span data-stu-id="83e99-204">Optional</span></span>              |

  <span data-ttu-id="83e99-205"><sup>1</sup> CQD では必須ではありませんが、テンプレートは建物とネットワーク名を表示するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="83e99-205"><sup>1</sup> While not required by CQD, the templates are configured to display Building and Network name.</span></span>

  <span data-ttu-id="83e99-206"><sup>2</sup> この設定は、サブネットが企業ネットワーク内にあるかどうかを反映するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="83e99-206"><sup>2</sup> This setting can be used to reflect whether or not the subnet is inside the corporate network.</span></span> <span data-ttu-id="83e99-207">他の目的に合わせて使用状況をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="83e99-207">You can customize usage for other purposes.</span></span>

  <span data-ttu-id="83e99-208"><sup>3</sup> この設定は、ネットワークが Azure ExpressRoute を使用するかどうかを反映するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="83e99-208"><sup>3</sup> This setting can be used to reflect whether or not the network uses Azure ExpressRoute.</span></span> <span data-ttu-id="83e99-209">他の目的に合わせて使用状況をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="83e99-209">You can customize usage for other purposes.</span></span>  

  <span data-ttu-id="83e99-210">**サンプル行:**</span><span class="sxs-lookup"><span data-stu-id="83e99-210">**Sample row:**</span></span>

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> <span data-ttu-id="83e99-211">ネットワーク範囲は、スーパーネット (複数のサブネットと 1 つのルーティング プレフィックスの組み合わせ) を表す場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="83e99-211">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="83e99-212">新しい建物のアップロードはすべて、重複する範囲がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="83e99-212">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="83e99-213">以前に建物のファイルをアップロードした場合は、現在のファイルをダウンロードし、もう一度アップロードして重複を特定し、もう一度アップロードする前に問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-213">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="83e99-214">以前にアップロードしたファイルで重複すると、レポート内の建物に対するサブネットのマッピングが間違っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-214">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="83e99-215">VPN の実装によっては、サブネット情報が正確に報告されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-215">Certain VPN implementations do not accurately report the subnet information.</span></span> 
>
> <span data-ttu-id="83e99-216">VPN 列は省略可能で、既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="83e99-216">The VPN column is optional and will default to 0.</span></span> <span data-ttu-id="83e99-217">VPN 列の値が 1 に設定されている場合、その行で表されるサブネットは、サブネット内のすべての IP アドレスと一致するために完全に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="83e99-217">If the VPN column’s value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="83e99-218">これらのサブネットを完全に拡張すると、データの構築に関連するクエリのクエリ時間に悪影響を与えるので、VPN サブネットでのみ、この方法は注意して使用してください。</span><span class="sxs-lookup"><span data-stu-id="83e99-218">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>


### <a name="supernetting"></a><span data-ttu-id="83e99-219">スーパーネット</span><span class="sxs-lookup"><span data-stu-id="83e99-219">Supernetting</span></span>

<span data-ttu-id="83e99-220">各サブネットを定義する代Inter-Domainクラスレス ルーティング (CIDR) と呼ばれるスーパーネットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="83e99-220">You can use supernetting, commonly called Classless Inter-Domain Routing (CIDR,) in place of defining each subnet.</span></span> <span data-ttu-id="83e99-221">スーパー *ネットとは、1* つのルーティング プレフィックスを共有する複数のサブネットの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="83e99-221">A *supernet* is a combination of several subnets that share a single routing prefix.</span></span> <span data-ttu-id="83e99-222">サブネットごとにエントリを追加する代わりに、スーパーネットアドレスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="83e99-222">Instead of adding an entry for each subnet, you can use the supernetted address.</span></span> <span data-ttu-id="83e99-223">スーパーネット機能はサポートされますが、使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="83e99-223">Supernetting is supported, but we don't recommend using it.</span></span>

<span data-ttu-id="83e99-224">たとえば、Contoso のマーケティングビルは、次のサブネットで構成されています。</span><span class="sxs-lookup"><span data-stu-id="83e99-224">For example, Contoso's marketing building is made up of the subnets below:</span></span>

-   <span data-ttu-id="83e99-225">10.1.0.0/24— 1 階</span><span class="sxs-lookup"><span data-stu-id="83e99-225">10.1.0.0/24—first floor</span></span>
-   <span data-ttu-id="83e99-226">10.1.1.0/24— 2 階</span><span class="sxs-lookup"><span data-stu-id="83e99-226">10.1.1.0/24—second floor</span></span>
-   <span data-ttu-id="83e99-227">10.1.2.0/24- 3 階</span><span class="sxs-lookup"><span data-stu-id="83e99-227">10.1.2.0/24—third floor</span></span>
-   <span data-ttu-id="83e99-228">10.1.3.0/24 - 4 階</span><span class="sxs-lookup"><span data-stu-id="83e99-228">10.1.3.0/24—fourth floor</span></span>

<span data-ttu-id="83e99-229">この例では、サブネットごとにエントリを追加する代わりに、スーパーネットアドレス (10.1.0.0/22) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="83e99-229">Instead of adding an entry for each subnet, you can use the supernetted address—in this example, 10.1.0.0/22.</span></span>

-   <span data-ttu-id="83e99-230">ネットワーク = 10.1.0.0</span><span class="sxs-lookup"><span data-stu-id="83e99-230">Network = 10.1.0.0</span></span>
-   <span data-ttu-id="83e99-231">ネットワーク範囲 = 22</span><span class="sxs-lookup"><span data-stu-id="83e99-231">Network Range = 22</span></span>

<span data-ttu-id="83e99-232">スーパーネットを実装する前に、次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-232">Here are a few things to consider before you implement supernetting:</span></span>

-   <span data-ttu-id="83e99-233">スーパーネットは、8 ビットから 28 ビットマスクのサブネット マッピングでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="83e99-233">Supernetting can only be used in a subnet mapping with 8-bit to 28-bit mask.</span></span>

-   <span data-ttu-id="83e99-234">スーパーネット化は、前もって行う時間を短縮しますが、データのリッチ度を下げるときのコストがかかります。</span><span class="sxs-lookup"><span data-stu-id="83e99-234">Supernetting takes less time up front, but it comes at the cost of reducing the richness of your data.</span></span> <span data-ttu-id="83e99-235">たとえば、サブネット 10.1.2.0 に関する品質の問題が発生したとします。</span><span class="sxs-lookup"><span data-stu-id="83e99-235">Let's say there's a quality problem involving subnet 10.1.2.0.</span></span> <span data-ttu-id="83e99-236">スーパーネットを実装した場合、建物のどこにサブネットが保存されているのか、またどの種類のネットワーク (ラボなど) なのかがわかりません。</span><span class="sxs-lookup"><span data-stu-id="83e99-236">If you implemented supernetting, you won't know where in the building the subnet is located or what type of network it is (for example, a lab).</span></span> <span data-ttu-id="83e99-237">建物のすべてのサブネットを定義し、フロアの場所情報をアップロードした場合は、その違いを確認できます。</span><span class="sxs-lookup"><span data-stu-id="83e99-237">If you'd defined all the subnets for a building and uploaded floor location information, you'd be able to see that distinction.</span></span>

-   <span data-ttu-id="83e99-238">スーパーネットアドレスが正しく、不要なサブネットが検出されるのを防することが重要です。</span><span class="sxs-lookup"><span data-stu-id="83e99-238">It's important to ensure that the supernetted address is correct and isn't catching unwanted subnets.</span></span>

-   <span data-ttu-id="83e99-239">データで 192.168.0.0 を見つけるのは非常に一般的です。</span><span class="sxs-lookup"><span data-stu-id="83e99-239">It's quite common to find 192.168.0.0 in data.</span></span> <span data-ttu-id="83e99-240">多くの組織では、ユーザーが自宅にいます。</span><span class="sxs-lookup"><span data-stu-id="83e99-240">For many organizations, this indicates that the user is at home.</span></span> <span data-ttu-id="83e99-241">その他の場合、これは、衛星オフィスの IP アドレス スキームです。</span><span class="sxs-lookup"><span data-stu-id="83e99-241">For others, this is the IP address scheme for a satellite office.</span></span> <span data-ttu-id="83e99-242">組織にこの構成を使用するオフィスがある場合、一般的なサブネットを使用してホームネットワークと内部ネットワークを区別するのが難しいため、建物ファイルに含め [ないことです](quality-of-experience-review-guide.md#common-subnets)。</span><span class="sxs-lookup"><span data-stu-id="83e99-242">If your organization does have offices that use this configuration, don't include it in your building file because it's difficult to distinguish between home and internal networks by using [common subnets](quality-of-experience-review-guide.md#common-subnets).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="83e99-243">ネットワーク範囲は、スーパーネットを表す場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="83e99-243">The network range can be used to represent a supernet.</span></span> <span data-ttu-id="83e99-244">新しい建物データ ファイルのアップロードはすべて、重複する範囲がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="83e99-244">All new building data file uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="83e99-245">以前に建物ファイルをアップロードした場合は、現在のファイルをダウンロードし、もう一度アップロードして重複を特定し、問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-245">If you've previously uploaded a building file, you should download the current file and upload it again to identify any overlaps and fix the issue.</span></span> <span data-ttu-id="83e99-246">以前にアップロードしたファイルで重複すると、レポート内の建物に対するサブネットのマッピングが間違っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-246">Any overlap in previously uploaded files might result in the wrong mappings of subnets to buildings in the reports.</span></span>

### <a name="vpn"></a><span data-ttu-id="83e99-247">VPN</span><span class="sxs-lookup"><span data-stu-id="83e99-247">VPN</span></span>

<span data-ttu-id="83e99-248">クライアントが Microsoft 365 または Office 365 に送信するエクスペリエンス (QoE) データの品質 (CQD データの送信元) には、VPN フラグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="83e99-248">The quality of experience (QoE) data that clients send to Microsoft 365 or Office 365—which is where CQD data is sourced from—includes a VPN flag.</span></span> <span data-ttu-id="83e99-249">CQD では、これは第 1 VPN と第 2 VPN ディメンションとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="83e99-249">CQD will see this as the First VPN and Second VPN dimensions.</span></span> <span data-ttu-id="83e99-250">ただし、このフラグは、登録された VPN ネットワーク アダプターがリモート アクセス アダプターであるという VPN ベンダーの Windows への報告に依存します。</span><span class="sxs-lookup"><span data-stu-id="83e99-250">However, this flag relies on VPN vendors' reporting to Windows that the VPN network adapter registered is a Remote Access adapter.</span></span> <span data-ttu-id="83e99-251">すべての VPN ベンダーがリモート アクセス アダプターを正しく登録しているのではありません。</span><span class="sxs-lookup"><span data-stu-id="83e99-251">Not all VPN vendors properly register Remote Access adapters.</span></span> <span data-ttu-id="83e99-252">この理由から、組み込みの VPN クエリ フィルターを使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-252">Because of this, you might not be able to use the built-in VPN query filters.</span></span> <span data-ttu-id="83e99-253">VPN サブネットを正確にマークして識別するには、上記で説明した VPN 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="83e99-253">Use the VPN column discussed above to accurately mark and identify VPN subnets.</span></span> <span data-ttu-id="83e99-254">また、VPN ネットワークにラベルを付け、レポートの識別を容易に行うのも良い方法です。</span><span class="sxs-lookup"><span data-stu-id="83e99-254">It is also good practice to label your VPN networks for easy identification in your reports.</span></span> <span data-ttu-id="83e99-255">VPN サブネットにラベルを付けるには、次の 2 つの例を示します。</span><span class="sxs-lookup"><span data-stu-id="83e99-255">Below are two examples of how to label your VPN subnets:</span></span>

- <span data-ttu-id="83e99-256">VPN サブネット **のこのフィールドに** 「VPN」と入力して、ネットワーク名を定義します。</span><span class="sxs-lookup"><span data-stu-id="83e99-256">Define a **Network Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![ネットワーク名を使用した VPN を示す、"VPN" レポートのスクリーンショット](media/qerguide-image-vpnnetworkname.png)

- <span data-ttu-id="83e99-258">VPN サブネット **のこのフィールドに** 「VPN」と入力して建物名を定義します。</span><span class="sxs-lookup"><span data-stu-id="83e99-258">Define a **Building Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![建物名を使用した VPN を示す、"VPN" レポートのスクリーンショット](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> <span data-ttu-id="83e99-260">VPN 接続では、基になる接続がワイヤレスの場合に、ネットワーク接続の種類が有線と誤って見なされるという問題が知られています。</span><span class="sxs-lookup"><span data-stu-id="83e99-260">VPN connections have been known to misidentify the network connection type as wired when the underlying connection is wireless.</span></span> <span data-ttu-id="83e99-261">VPN 接続で品質を確認する場合、接続の種類が正確に識別されたと想定できません。</span><span class="sxs-lookup"><span data-stu-id="83e99-261">When looking at quality over VPN connections, you can't assume that the connection type has been accurately identified.</span></span>

## <a name="endpoint-data-file"></a><span data-ttu-id="83e99-262">エンドポイント データ ファイル</span><span class="sxs-lookup"><span data-stu-id="83e99-262">Endpoint data file</span></span>

<span data-ttu-id="83e99-263">もう 1 つの種類の CQD テナント データ ファイルは **、エンドポイント データ ファイル** です。</span><span class="sxs-lookup"><span data-stu-id="83e99-263">The other type of CQD tenant data file is the **Endpoint** data file.</span></span> <span data-ttu-id="83e99-264">列の値は、通話レコードの [第 1 クライアント エンドポイント名] 列または [第 2 クライアント エンドポイント名] 列で、エンドポイントの作成、モデル、または種類の情報を表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="83e99-264">The column values are used in the call record’s First Client Endpoint Name or Second Client Endpoint Name column to show Endpoint Make, Model, or Type information.</span></span> <span data-ttu-id="83e99-265">アップロードするデータ ファイルの形式は、アップロード前に検証チェックに合格するには、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-265">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>

- <span data-ttu-id="83e99-266">ファイルは .tsv ファイル (列はタブで区切られています) または .csv ファイル (列はコンマで区切られています) のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-266">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="83e99-267">データ ファイルの内容には、テーブルの見出しは含されません。</span><span class="sxs-lookup"><span data-stu-id="83e99-267">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="83e99-268">データ ファイルの最初の行は、"EndpointName" のようなヘッダー ラベルではなく、実際のデータである必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-268">The first line of the data file is expected to be real data, not a header label like "EndpointName".</span></span>

- <span data-ttu-id="83e99-269">7 つの列はすべて文字列データ型のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="83e99-269">All seven columns use the String data type only.</span></span> <span data-ttu-id="83e99-270">許可される最大長は 64 文字です。</span><span class="sxs-lookup"><span data-stu-id="83e99-270">The maximum allowed length is 64 characters.</span></span>

- <span data-ttu-id="83e99-271">データ フィールドは空白でも、タブまたはコンマで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-271">A data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="83e99-272">空のデータ フィールドには、空の文字列値が割り当て込まれます。</span><span class="sxs-lookup"><span data-stu-id="83e99-272">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="83e99-273">EndpointName は一意である必要があります。そうしないと、アップロードは失敗します。</span><span class="sxs-lookup"><span data-stu-id="83e99-273">EndpointName must be unique, otherwise the upload fails.</span></span> <span data-ttu-id="83e99-274">同じ EndpointName を使用する重複する行または 2 つの行がある場合、競合は誤った結合の原因になります。</span><span class="sxs-lookup"><span data-stu-id="83e99-274">If there is a duplicate row or two rows that use the same EndpointName the conflict will  cause incorrect joining.</span></span>

- <span data-ttu-id="83e99-275">EndpointLabel1、EndpointLabel2、EndpointLabel3 はカスタマイズ可能なラベルです。</span><span class="sxs-lookup"><span data-stu-id="83e99-275">EndpointLabel1, EndpointLabel2, and EndpointLabel3 are customizable labels.</span></span> <span data-ttu-id="83e99-276">空の文字列や、"IT 部門が指定した 2018 Laptop" や "Asset Tag 5678" などの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="83e99-276">They can be empty Strings or values such as “IT Department designated 2018 Laptop” or “Asset Tag 5678”.</span></span>

- <span data-ttu-id="83e99-277">各行には 7 つの列が必要で、列は次の順序である必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-277">There must be seven columns for each row and the columns must be in the following order:</span></span>

  <span data-ttu-id="83e99-278">**フィールドの順序:**</span><span class="sxs-lookup"><span data-stu-id="83e99-278">**Field order:**</span></span>

  <span data-ttu-id="83e99-279">EndpointName、EndpointMake、EndpointModel、EndpointType、EndpointLabel1、EndpointLabel2、EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="83e99-279">EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2,  EndpointLabel3</span></span>

  <span data-ttu-id="83e99-280">**サンプル行:**</span><span class="sxs-lookup"><span data-stu-id="83e99-280">**Sample row:**</span></span>

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a><span data-ttu-id="83e99-281">建物ファイルを更新する</span><span class="sxs-lookup"><span data-stu-id="83e99-281">Update a building file</span></span>

<span data-ttu-id="83e99-282">管理者は、建物とサブネットの情報を収集しながら、時間の流れに応じて建物ファイルを複数回アップロードし、新しいサブネットとその建物情報が利用可能になったら追加します。</span><span class="sxs-lookup"><span data-stu-id="83e99-282">While gathering building and subnet information, administrators will often upload the building file in multiple iterations over time, adding new subnets and their building information as it becomes available.</span></span> <span data-ttu-id="83e99-283">この場合は、建物ファイルを再アップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-283">When this occurs, you'll need to re-upload your building file.</span></span> <span data-ttu-id="83e99-284">このプロセスは、前のセクションで説明したように、最初のアップロードと同じで、次のセクションで説明するいくつかの例外があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-284">This process is like the initial upload as described in the previous section, with a few exceptions as noted in the following section.</span></span>

> [!Important]
> <span data-ttu-id="83e99-285">一度にアクティブにできる建物ファイルは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="83e99-285">Only one building file can be active at a time.</span></span> <span data-ttu-id="83e99-286">複数の建物ファイルは累積ではありません。</span><span class="sxs-lookup"><span data-stu-id="83e99-286">Multiple building files aren't cumulative.</span></span>

## <a name="add-net-new-subnets"></a><span data-ttu-id="83e99-287">正味新しいサブネットを追加する</span><span class="sxs-lookup"><span data-stu-id="83e99-287">Add net new subnets</span></span>

<span data-ttu-id="83e99-288">ネットワーク トポロジの一部ではなかった正味新しいサブネットを CQD に追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-288">There are times when you'll need to add net new subnets to CQD that weren't originally part of your network topology.</span></span> <span data-ttu-id="83e99-289">正味新しいサブネットを追加するには、CQD の **[テナント** データのアップロード] ページから次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="83e99-289">To add net new subnets, do the following from the **Tenant Data Upload** page in CQD:</span></span>

1.  <span data-ttu-id="83e99-290">最新のコピーをまだインストールしていない場合は、元のファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="83e99-290">Download the original file, if you don't already have an up-to-date copy.</span></span>

1.  <span data-ttu-id="83e99-291">CQD で現在のファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="83e99-291">Remove the current file in CQD.</span></span>

1.  <span data-ttu-id="83e99-292">元の建物ファイルを編集し、正味新しいサブネットが取得される少なくとも 1 日前に終了日を指定します。</span><span class="sxs-lookup"><span data-stu-id="83e99-292">Edit the original building file and provide an end date that occurs at least one day before the net new subnets were acquired.</span></span>

1.  <span data-ttu-id="83e99-293">正味新しいサブネットを元の建物ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="83e99-293">Append the net new subnets to the original building file.</span></span>

1.  <span data-ttu-id="83e99-294">新しく変更した建物ファイルをアップロードし、前の建物ファイルが終了した 1 日後の開始日を設定します。</span><span class="sxs-lookup"><span data-stu-id="83e99-294">Upload the newly modified building file, and set the start date for one day after the previous building file ends.</span></span>

## <a name="add-missing-subnets"></a><span data-ttu-id="83e99-295">不足しているサブネットを追加する</span><span class="sxs-lookup"><span data-stu-id="83e99-295">Add missing subnets</span></span>

<span data-ttu-id="83e99-296">管理ネットワークの建物情報をアップロードした後は、すべての管理ネットワークに建物の関連付けを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-296">After you upload building information for managed networks, every managed network should have a building association.</span></span> <span data-ttu-id="83e99-297">ただし、必ずしもそうではありません。通常、一部のサブネットは表示されません。</span><span class="sxs-lookup"><span data-stu-id="83e99-297">However, this won't always be the case; typically, a few subnets are missed.</span></span> <span data-ttu-id="83e99-298">不足しているネットワークを見つけるには、CQD の [Quality **of Experience Reports]** ページで不足しているサブネット レポートを確認します。 </span><span class="sxs-lookup"><span data-stu-id="83e99-298">To find these missing networks, review the **Missing Subnet Report** on the **Quality of Experience Reports** page in CQD.</span></span> <span data-ttu-id="83e99-299">これにより、建物データ ファイルで定義されていない、外部としてマークされている 10 以上のオーディオ ストリームを持つすべてのサブネットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="83e99-299">This presents all the subnets with 10 or more audio streams that aren't defined in the building data file and are being marked as outside.</span></span> <span data-ttu-id="83e99-300">このリストに管理対象ネットワークが含まれるなか確認します。</span><span class="sxs-lookup"><span data-stu-id="83e99-300">Ensure that there are no managed networks in this list.</span></span> <span data-ttu-id="83e99-301">サブネットが見つからない場合は、次の手順に従って、元の建物データ ファイルを更新し、CQD に再アップロードします。</span><span class="sxs-lookup"><span data-stu-id="83e99-301">If subnets are missing, use the following procedure to update the original building data file and re-upload it to CQD.</span></span>

1. <span data-ttu-id="83e99-302">CQD **の [テナント データのアップロード** ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="83e99-302">Go to the **Tenant Data Upload** page in CQD.</span></span>

1. <span data-ttu-id="83e99-303">最新のコピーをまだインストールしていない場合は、元のファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="83e99-303">Download the original file, if you don't already have an up-to-date copy.</span></span>

1. <span data-ttu-id="83e99-304">CQD で現在のファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="83e99-304">Remove the current file in CQD.</span></span>

1. <span data-ttu-id="83e99-305">新しいサブネットを元のファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="83e99-305">Append the new subnets to the original file.</span></span>

1. <span data-ttu-id="83e99-306">建物ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="83e99-306">Upload the building file.</span></span> <span data-ttu-id="83e99-307">CQD が履歴データを処理するには、少なくとも 8 か月前に開始日を設定してください。</span><span class="sxs-lookup"><span data-stu-id="83e99-307">Be sure to set the start date to at least eight months prior so that CQD will process historical data.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="83e99-308">レポートをフィルター処理して組織のテナント データのみを表示するには、このレポートに第 2 テナント ID のクエリ フィルターとしてテナント **ID** を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83e99-308">You'll need to add your tenant ID as a query filter for **Second Tenant ID** to this report to filter the report to view only your organization's tenant data.</span></span> <span data-ttu-id="83e99-309">それ以外の場合、レポートにはフェデレーションサブネットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="83e99-309">Otherwise, the report will show federated subnets.</span></span>

> [!NOTE] 
> <span data-ttu-id="83e99-310">Month Year レポート フィルターを現在の月に調整してください。</span><span class="sxs-lookup"><span data-stu-id="83e99-310">Be sure to adjust the Month Year report filter to the current month.</span></span> <span data-ttu-id="83e99-311">[ **編集] を** 選択し、月の **レポート フィルター** を調整して、新しい既定の月を保存します。</span><span class="sxs-lookup"><span data-stu-id="83e99-311">Select **Edit**, and adjust the **Month Year** report filter to save the new default month.</span></span>


## <a name="related-topics"></a><span data-ttu-id="83e99-312">関連項目</span><span class="sxs-lookup"><span data-stu-id="83e99-312">Related topics</span></span>

[<span data-ttu-id="83e99-313">CQD の建物マップを作成する</span><span class="sxs-lookup"><span data-stu-id="83e99-313">Create a building map for CQD</span></span>](CQD-building-mapping.md)

[<span data-ttu-id="83e99-314">Teams の通話品質の向上と監視</span><span class="sxs-lookup"><span data-stu-id="83e99-314">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="83e99-315">CQD とは</span><span class="sxs-lookup"><span data-stu-id="83e99-315">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="83e99-316">通話品質ダッシュボード (CQD) を設定する</span><span class="sxs-lookup"><span data-stu-id="83e99-316">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="83e99-317">CQD データとレポート</span><span class="sxs-lookup"><span data-stu-id="83e99-317">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="83e99-318">CQD を使用して通話と会議の品質を管理する</span><span class="sxs-lookup"><span data-stu-id="83e99-318">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="83e99-319">CQD で使用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="83e99-319">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="83e99-320">CQD でのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="83e99-320">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="83e99-321">Power BI を使用して CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="83e99-321">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
