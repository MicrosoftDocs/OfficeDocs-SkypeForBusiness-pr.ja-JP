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
description: 通話品質ダッシュボード (CQD) でテナントと建物のデータをアップロードする方法について説明します。
ms.openlocfilehash: 50a059f78a2d719d5d9106a755dbcf6ac8044d1b
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908696"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a><span data-ttu-id="ddd43-103">通話品質ダッシュボード (CQD) でテナントと建物のデータをアップロードする</span><span class="sxs-lookup"><span data-stu-id="ddd43-103">Upload tenant and building data in Call Quality Dashboard (CQD)</span></span>


<span data-ttu-id="ddd43-104">通話品質ダッシュボード (CQD) を最大限に活用するには、テナントをアップロードし、データを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ddd43-104">To get the most out of Call Quality Dashboard (CQD), we recommend that you upload your tenant and building data.</span></span> <span data-ttu-id="ddd43-105">テナントデータファイルには、 [ビルド](#upload-building-data-file) と [エンドポイント](#endpoint-data-file)の2種類があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-105">There are 2 types of tenant data files, [Building](#upload-building-data-file) and [Endpoint](#endpoint-data-file).</span></span>

<span data-ttu-id="ddd43-106">サンプルテナントデータテンプレートは、 [ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-106">You can download a sample tenant data template [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).</span></span> <span data-ttu-id="ddd43-107">文書のマッピングの詳細については、「 [CQD の文書パーツを作成](CQD-building-mapping.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddd43-107">For help with building mapping, read [Create a building map for CQD](CQD-building-mapping.md).</span></span>

<span data-ttu-id="ddd43-108">CQD Summary レポートダッシュボードで、[CQD **Settings** ] メニュー (CQD の上部にある歯車アイコン) から [ **テナントデータアップロード** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-108">From the CQD Summary Reports dashboard, select **Tenant Data Upload** from the CQD **Settings** menu (a gear icon at the top of CQD).</span></span> <span data-ttu-id="ddd43-109">ここでは、管理者は、IP アドレスと地理的情報のマッピング、各ワイヤレスアクセスポイントと MAC アドレスのマッピングなど、組織の建物とエンドポイントの情報をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-109">From here, admins can upload their organization's building and endpoint information, such as mapping of IP addresses and geographical information, mapping each wireless access point and its MAC address, etc.</span></span>

1. <span data-ttu-id="ddd43-110">CQD (Teams 管理センターまたは at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) ) を開き、右上隅にある歯車アイコンを選んで、[ **概要レポート** ] ページから [ **テナントデータアップロード** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-110">Open CQD (from the Teams admin center, or at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)), then select the gear icon in the upper-right corner and choose **Tenant Data Upload** from the **Summary Reports** page.</span></span>

   ![データのアップロード中に表示されるダイアログボックスのスクリーンショット](media/qerguide-image-tenantdataupload.png)
    
2. <span data-ttu-id="ddd43-112">また、初めて CQD にアクセスする場合は、建物のデータをアップロードするように求められます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-112">Alternatively, if this is your first time visiting CQD, you'll be asked to upload building data.</span></span> <span data-ttu-id="ddd43-113">[ **今すぐアップロード** ] を選択すると、[ **テナントデータアップロード** ] ページにすばやく移動できます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-113">You can select **Upload Now** to quickly navigate to the **Tenant Data Upload** page.</span></span>

   ![建物のデータをアップロードするようにユーザーに通知するバナーのスクリーンショット](media/qerguide-image-buildingdatauploadbanner.png)

3. <span data-ttu-id="ddd43-115">[ **テナントデータのアップロード** ] ページで、[ **参照** ] を選んでデータファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-115">On the **Tenant Data Upload** page, select **Browse** to choose a data file.</span></span>

4. <span data-ttu-id="ddd43-116">データファイルを選択した後、[ **開始日** ] を指定し、必要に応じて終了日を指定します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-116">After selecting a data file, specify **Start date** and, optionally, specify an end date.</span></span>

5. <span data-ttu-id="ddd43-117">[ **開始日** ] を選んだら、[ **アップロード** ] を選んでファイルを CQD にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="ddd43-117">After selecting **Start date** , select **Upload** to upload the file to CQD.</span></span> <br><br><span data-ttu-id="ddd43-118">ファイルがアップロードされる前に、ファイルが検証されます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-118">Before the file is uploaded, it's validated.</span></span> <span data-ttu-id="ddd43-119">検証に失敗した場合は、ファイルを修正するように求めるエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-119">If validation fails, an error message is displayed requesting that you correct the file.</span></span> <span data-ttu-id="ddd43-120">次の図は、データファイルの列数が正しくない場合に発生するエラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="ddd43-120">The following figure shows an error occurring when the number of columns in the data file is incorrect.</span></span>

   ![文書のデータアップロードエラーが表示されたダイアログボックスの例](media/qerguide-image-buildingdatauploaderror.png)
 
6. <span data-ttu-id="ddd43-122">検証中にエラーが発生しなかった場合、ファイルのアップロードは成功します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-122">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="ddd43-123">アップロードしたデータファイルが **[マイアップロード** ] テーブルに表示されます。これにより、そのページの下部にある現在のテナントのすべてのアップロードされたファイルの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-123">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>

> [!NOTE]
> <span data-ttu-id="ddd43-124">ビルドファイルの処理が完了するまでに最大で4時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-124">It can take up to four hours to finish processing the building file.</span></span> <br><br> <span data-ttu-id="ddd43-125">既に文書ファイルをアップロードしていて、見つからないか除外されている可能性のあるサブネットを追加する必要がある場合は、新しいサブネットを追加して元のファイルを変更し、現在のファイルを削除し、新しく編集したファイルを再アップロードします。</span><span class="sxs-lookup"><span data-stu-id="ddd43-125">If you've already uploaded a building file and need to add subnets that might have been missed or excluded, modify the original file by adding the new subnets, remove the current file, and re-upload the newly edited file.</span></span> <span data-ttu-id="ddd43-126">CQD には、アクティブな建物データファイルは1つしか存在できません。</span><span class="sxs-lookup"><span data-stu-id="ddd43-126">There can be only one active building data file in CQD.</span></span> 


## <a name="upload-building-data-file"></a><span data-ttu-id="ddd43-127">建物のデータファイルをアップロードする</span><span class="sxs-lookup"><span data-stu-id="ddd43-127">Upload building data file</span></span>

<span data-ttu-id="ddd43-128">CQD のテナントデータファイルの最初の種類は、 **建物** データファイルです。</span><span class="sxs-lookup"><span data-stu-id="ddd43-128">The first type of tenant data file in CQD is the **Building** data file.</span></span> <span data-ttu-id="ddd43-129">[Subnet] 列を抽出するには、Network + NetworkRange 列を展開し、サブネット列を通話レコードの最初のサブネットまたは第2サブネット列に結合して、建物、市区町村、国、または地域の情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-129">The Subnet column is derived by expanding the Network+NetworkRange column, then joining the Subnet column to the call record’s First Subnet or Second Subnet column to show Building, City, Country, or Region information.</span></span> <span data-ttu-id="ddd43-130">アップロードするデータファイルの形式は、次の条件に従って、アップロード前に検証チェックに合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-130">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>
  
- <span data-ttu-id="ddd43-131">ファイルは、.tsv ファイル (列はタブで区切られます) または .csv ファイル (列はコンマで区切られます) のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-131">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="ddd43-132">データファイルには、テーブルの見出し行が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="ddd43-132">The data file doesn't include a table header row.</span></span> <span data-ttu-id="ddd43-133">データファイルの最初の行は、"Network" のようなヘッダーラベルではなく、実際のデータであると想定されています。</span><span class="sxs-lookup"><span data-stu-id="ddd43-133">The first line of the data file is expected to be real data, not header labels like "Network".</span></span>

- <span data-ttu-id="ddd43-134">ファイル内のデータ型に指定できるのは、String、Integer、またはブール値のみです。</span><span class="sxs-lookup"><span data-stu-id="ddd43-134">Data types in the file can only be String, Integer, or Boolean.</span></span> <span data-ttu-id="ddd43-135">整数データ型の場合、値は数値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-135">For the  Integer data type, the value must be a numeric value.</span></span> <span data-ttu-id="ddd43-136">ブール値は、0または1でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="ddd43-136">Boolean values must be either 0 or 1.</span></span>

- <span data-ttu-id="ddd43-137">列に文字列データ型が使用されている場合、データフィールドは空でもかまいませんが、タブまたはコンマで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-137">If a column uses the String data type, a data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="ddd43-138">空のデータフィールドでは、空の文字列値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-138">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="ddd43-139">各行には14個の列がある必要があります。各列のデータ型は適切であり、列の順序は、次の表の順序になっている必要があります (カンマまたはタブ区切り)。</span><span class="sxs-lookup"><span data-stu-id="ddd43-139">There must be 14 columns for each row, each column must have the appropriate data type, and the columns must be in the order listed in the following table (comma or tab delimited):</span></span>

  <span data-ttu-id="ddd43-140">**データファイル形式の作成**</span><span class="sxs-lookup"><span data-stu-id="ddd43-140">**Building data file format**</span></span>
  
  | <span data-ttu-id="ddd43-141">列名</span><span class="sxs-lookup"><span data-stu-id="ddd43-141">Column name</span></span>        | <span data-ttu-id="ddd43-142">データ型</span><span class="sxs-lookup"><span data-stu-id="ddd43-142">Data type</span></span> | <span data-ttu-id="ddd43-143">例</span><span class="sxs-lookup"><span data-stu-id="ddd43-143">Example</span></span>                   | <span data-ttu-id="ddd43-144">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="ddd43-144">Guidance</span></span>              |
  |--------------------|-----------|---------------------------|-----------------------|
  | <span data-ttu-id="ddd43-145">NetworkIP</span><span class="sxs-lookup"><span data-stu-id="ddd43-145">NetworkIP</span></span>          | <span data-ttu-id="ddd43-146">文字列</span><span class="sxs-lookup"><span data-stu-id="ddd43-146">String</span></span>    | <span data-ttu-id="ddd43-147">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="ddd43-147">192.168.1.0</span></span>               | <span data-ttu-id="ddd43-148">必須</span><span class="sxs-lookup"><span data-stu-id="ddd43-148">Required</span></span>              |
  | <span data-ttu-id="ddd43-149">NetworkName</span><span class="sxs-lookup"><span data-stu-id="ddd43-149">NetworkName</span></span>        | <span data-ttu-id="ddd43-150">文字列</span><span class="sxs-lookup"><span data-stu-id="ddd43-150">String</span></span>    | <span data-ttu-id="ddd43-151">米国/シアトル/シアトル-SEA-1</span><span class="sxs-lookup"><span data-stu-id="ddd43-151">USA/Seattle/SEATTLE-SEA-1</span></span> | <span data-ttu-id="ddd43-152">必須<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ddd43-152">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="ddd43-153">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="ddd43-153">NetworkRange</span></span>       | <span data-ttu-id="ddd43-154">数値</span><span class="sxs-lookup"><span data-stu-id="ddd43-154">Number</span></span>    | <span data-ttu-id="ddd43-155">#</span><span class="sxs-lookup"><span data-stu-id="ddd43-155">26</span></span>                        | <span data-ttu-id="ddd43-156">必須</span><span class="sxs-lookup"><span data-stu-id="ddd43-156">Required</span></span>              |
  | <span data-ttu-id="ddd43-157">BuildingName</span><span class="sxs-lookup"><span data-stu-id="ddd43-157">BuildingName</span></span>       | <span data-ttu-id="ddd43-158">文字列</span><span class="sxs-lookup"><span data-stu-id="ddd43-158">String</span></span>    | <span data-ttu-id="ddd43-159">シアトル-SEA-1</span><span class="sxs-lookup"><span data-stu-id="ddd43-159">SEATTLE-SEA-1</span></span>             | <span data-ttu-id="ddd43-160">必須<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ddd43-160">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="ddd43-161">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="ddd43-161">OwnershipType</span></span>      | <span data-ttu-id="ddd43-162">文字列</span><span class="sxs-lookup"><span data-stu-id="ddd43-162">String</span></span>    | <span data-ttu-id="ddd43-163">コントソ</span><span class="sxs-lookup"><span data-stu-id="ddd43-163">Contoso</span></span>                   | <span data-ttu-id="ddd43-164">省略可能</span><span class="sxs-lookup"><span data-stu-id="ddd43-164">Optional</span></span>              |
  | <span data-ttu-id="ddd43-165">BuildingType</span><span class="sxs-lookup"><span data-stu-id="ddd43-165">BuildingType</span></span>       | <span data-ttu-id="ddd43-166">文字列</span><span class="sxs-lookup"><span data-stu-id="ddd43-166">String</span></span>    | <span data-ttu-id="ddd43-167">IT の終了</span><span class="sxs-lookup"><span data-stu-id="ddd43-167">IT Termination</span></span>            | <span data-ttu-id="ddd43-168">省略可能</span><span class="sxs-lookup"><span data-stu-id="ddd43-168">Optional</span></span>              |
  | <span data-ttu-id="ddd43-169">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="ddd43-169">BuildingOfficeType</span></span> | <span data-ttu-id="ddd43-170">文字列</span><span class="sxs-lookup"><span data-stu-id="ddd43-170">String</span></span>    | <span data-ttu-id="ddd43-171">エンジニアリング</span><span class="sxs-lookup"><span data-stu-id="ddd43-171">Engineering</span></span>               | <span data-ttu-id="ddd43-172">省略可能</span><span class="sxs-lookup"><span data-stu-id="ddd43-172">Optional</span></span>              |
  | <span data-ttu-id="ddd43-173">市区町村</span><span class="sxs-lookup"><span data-stu-id="ddd43-173">City</span></span>               | <span data-ttu-id="ddd43-174">文字列</span><span class="sxs-lookup"><span data-stu-id="ddd43-174">String</span></span>    | <span data-ttu-id="ddd43-175">調布市調布ヶ丘</span><span class="sxs-lookup"><span data-stu-id="ddd43-175">Seattle</span></span>                   | <span data-ttu-id="ddd43-176">推奨</span><span class="sxs-lookup"><span data-stu-id="ddd43-176">Recommended</span></span>           |
  | <span data-ttu-id="ddd43-177">ZipCode</span><span class="sxs-lookup"><span data-stu-id="ddd43-177">ZipCode</span></span>            | <span data-ttu-id="ddd43-178">文字列</span><span class="sxs-lookup"><span data-stu-id="ddd43-178">String</span></span>    | <span data-ttu-id="ddd43-179">98001</span><span class="sxs-lookup"><span data-stu-id="ddd43-179">98001</span></span>                     | <span data-ttu-id="ddd43-180">推奨</span><span class="sxs-lookup"><span data-stu-id="ddd43-180">Recommended</span></span>           |
  | <span data-ttu-id="ddd43-181">居住</span><span class="sxs-lookup"><span data-stu-id="ddd43-181">Country</span></span>            | <span data-ttu-id="ddd43-182">文字列</span><span class="sxs-lookup"><span data-stu-id="ddd43-182">String</span></span>    | <span data-ttu-id="ddd43-183">プロセッサー</span><span class="sxs-lookup"><span data-stu-id="ddd43-183">US</span></span>                        | <span data-ttu-id="ddd43-184">推奨</span><span class="sxs-lookup"><span data-stu-id="ddd43-184">Recommended</span></span>           |
  | <span data-ttu-id="ddd43-185">都道府県</span><span class="sxs-lookup"><span data-stu-id="ddd43-185">State</span></span>              | <span data-ttu-id="ddd43-186">文字列</span><span class="sxs-lookup"><span data-stu-id="ddd43-186">String</span></span>    | <span data-ttu-id="ddd43-187">WA</span><span class="sxs-lookup"><span data-stu-id="ddd43-187">WA</span></span>                        | <span data-ttu-id="ddd43-188">推奨</span><span class="sxs-lookup"><span data-stu-id="ddd43-188">Recommended</span></span>           |
  | <span data-ttu-id="ddd43-189">Region</span><span class="sxs-lookup"><span data-stu-id="ddd43-189">Region</span></span>             | <span data-ttu-id="ddd43-190">文字列</span><span class="sxs-lookup"><span data-stu-id="ddd43-190">String</span></span>    | <span data-ttu-id="ddd43-191">MSUS</span><span class="sxs-lookup"><span data-stu-id="ddd43-191">MSUS</span></span>                      | <span data-ttu-id="ddd43-192">推奨</span><span class="sxs-lookup"><span data-stu-id="ddd43-192">Recommended</span></span>           |
  | <span data-ttu-id="ddd43-193">InsideCorp<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ddd43-193">InsideCorp<sup>2</sup></span></span>         | <span data-ttu-id="ddd43-194">ブール</span><span class="sxs-lookup"><span data-stu-id="ddd43-194">Bool</span></span>      | <span data-ttu-id="ddd43-195">1</span><span class="sxs-lookup"><span data-stu-id="ddd43-195">1</span></span>             | <span data-ttu-id="ddd43-196">必須</span><span class="sxs-lookup"><span data-stu-id="ddd43-196">Required</span></span>              |
  | <span data-ttu-id="ddd43-197">ExpressRoute<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ddd43-197">ExpressRoute<sup>3</sup></span></span>       | <span data-ttu-id="ddd43-198">ブール</span><span class="sxs-lookup"><span data-stu-id="ddd43-198">Bool</span></span>      | <span data-ttu-id="ddd43-199">0</span><span class="sxs-lookup"><span data-stu-id="ddd43-199">0</span></span>             | <span data-ttu-id="ddd43-200">必須</span><span class="sxs-lookup"><span data-stu-id="ddd43-200">Required</span></span>              |
  | <span data-ttu-id="ddd43-201">VPN</span><span class="sxs-lookup"><span data-stu-id="ddd43-201">VPN</span></span>                | <span data-ttu-id="ddd43-202">ブール</span><span class="sxs-lookup"><span data-stu-id="ddd43-202">Bool</span></span>      | <span data-ttu-id="ddd43-203">0</span><span class="sxs-lookup"><span data-stu-id="ddd43-203">0</span></span>                         | <span data-ttu-id="ddd43-204">省略可能</span><span class="sxs-lookup"><span data-stu-id="ddd43-204">Optional</span></span>              |

  <span data-ttu-id="ddd43-205"><sup>1</sup> CQD では必須ではありませんが、テンプレートは、建物とネットワーク名を表示するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="ddd43-205"><sup>1</sup> While not required by CQD, the templates are configured to display Building and Network name.</span></span>

  <span data-ttu-id="ddd43-206"><sup>2</sup> この設定を使用すると、サブネットが企業ネットワーク内にあるかどうかを反映できます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-206"><sup>2</sup> This setting can be used to reflect whether or not the subnet is inside the corporate network.</span></span> <span data-ttu-id="ddd43-207">他の目的で使用をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-207">You can customize usage for other purposes.</span></span>

  <span data-ttu-id="ddd43-208"><sup>3</sup> この設定を使用すると、ネットワークが Azure ExpressRoute を使用しているかどうかを反映できます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-208"><sup>3</sup> This setting can be used to reflect whether or not the network uses Azure ExpressRoute.</span></span> <span data-ttu-id="ddd43-209">他の目的で使用をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-209">You can customize usage for other purposes.</span></span>  

  <span data-ttu-id="ddd43-210">**サンプルの行:**</span><span class="sxs-lookup"><span data-stu-id="ddd43-210">**Sample row:**</span></span>

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> <span data-ttu-id="ddd43-211">ネットワーク範囲は、スーパーネット (単一のルーティングプレフィックスを持つ複数のサブネットの組み合わせ) を表すために使用できます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-211">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="ddd43-212">新しくなったすべての文書のアップロードで、重複範囲が確認されます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-212">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="ddd43-213">以前にビルドファイルをアップロードしたことがある場合は、現在のファイルをダウンロードして再アップロードし、重複を特定し、問題を解決してからもう一度アップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-213">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="ddd43-214">以前にアップロードされたファイルが重なっていると、サブネットとレポートの建物とのマッピングが間違っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-214">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="ddd43-215">特定の VPN の実装では、サブネット情報が正確に報告されません。</span><span class="sxs-lookup"><span data-stu-id="ddd43-215">Certain VPN implementations do not accurately report the subnet information.</span></span> 
>
> <span data-ttu-id="ddd43-216">VPN 列はオプションであり、既定値は0に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-216">The VPN column is optional and will default to 0.</span></span> <span data-ttu-id="ddd43-217">VPN 列の値が1に設定されている場合、その行で表されるサブネットは、サブネット内のすべての IP アドレスと一致するように完全に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-217">If the VPN column’s value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="ddd43-218">これらのサブネットを完全に拡張すると、データの作成に関係するクエリのクエリ時間に悪影響を与える可能性があるため、このように慎重に使用してください。</span><span class="sxs-lookup"><span data-stu-id="ddd43-218">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>


### <a name="supernetting"></a><span data-ttu-id="ddd43-219">スーパー</span><span class="sxs-lookup"><span data-stu-id="ddd43-219">Supernetting</span></span>

<span data-ttu-id="ddd43-220">スーパーネット化 (一般的にはクラスレス Inter-Domain ルーティング (CIDR)) を使って、各サブネットの定義の代わりに使用できます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-220">You can use supernetting, commonly called Classless Inter-Domain Routing (CIDR,) in place of defining each subnet.</span></span> <span data-ttu-id="ddd43-221">*スーパーネット* は、単一のルーティングプレフィックスを共有する複数のサブネットの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="ddd43-221">A *supernet* is a combination of several subnets that share a single routing prefix.</span></span> <span data-ttu-id="ddd43-222">サブネットごとにエントリを追加する代わりに、supernetted 住所を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-222">Instead of adding an entry for each subnet, you can use the supernetted address.</span></span> <span data-ttu-id="ddd43-223">スーパーネッティングはサポートされていますが、使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="ddd43-223">Supernetting is supported, but we don't recommend using it.</span></span>

<span data-ttu-id="ddd43-224">たとえば、Contoso のマーケティング用建物は以下のサブネットで構成されています。</span><span class="sxs-lookup"><span data-stu-id="ddd43-224">For example, Contoso's marketing building is made up of the subnets below:</span></span>

-   <span data-ttu-id="ddd43-225">10.1.0.0/24: 第1階</span><span class="sxs-lookup"><span data-stu-id="ddd43-225">10.1.0.0/24—first floor</span></span>
-   <span data-ttu-id="ddd43-226">10.1.1.0/24: 第2階</span><span class="sxs-lookup"><span data-stu-id="ddd43-226">10.1.1.0/24—second floor</span></span>
-   <span data-ttu-id="ddd43-227">10.1.2.0/24: 3 階</span><span class="sxs-lookup"><span data-stu-id="ddd43-227">10.1.2.0/24—third floor</span></span>
-   <span data-ttu-id="ddd43-228">10.1.3.0/24: 4 階</span><span class="sxs-lookup"><span data-stu-id="ddd43-228">10.1.3.0/24—fourth floor</span></span>

<span data-ttu-id="ddd43-229">サブネットごとにエントリを追加する代わりに、supernetted 住所 (この例では 10.1.0.0/22) を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-229">Instead of adding an entry for each subnet, you can use the supernetted address—in this example, 10.1.0.0/22.</span></span>

-   <span data-ttu-id="ddd43-230">Network = 10.1.0.0</span><span class="sxs-lookup"><span data-stu-id="ddd43-230">Network = 10.1.0.0</span></span>
-   <span data-ttu-id="ddd43-231">ネットワーク範囲 = 22</span><span class="sxs-lookup"><span data-stu-id="ddd43-231">Network Range = 22</span></span>

<span data-ttu-id="ddd43-232">スーパーネッティングを実装する前に、次の点について考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-232">Here are a few things to consider before you implement supernetting:</span></span>

-   <span data-ttu-id="ddd43-233">スーパーネッティングは、8ビットから28ビットのマスクを持つサブネットマッピングでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-233">Supernetting can only be used in a subnet mapping with 8-bit to 28-bit mask.</span></span>

-   <span data-ttu-id="ddd43-234">スーパーネッティングでは時間が短くなりますが、データの量を削減するためのコストがかかります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-234">Supernetting takes less time up front, but it comes at the cost of reducing the richness of your data.</span></span> <span data-ttu-id="ddd43-235">サブネット10.1.2.0 に関する音質の問題が発生したとします。</span><span class="sxs-lookup"><span data-stu-id="ddd43-235">Let's say there's a quality problem involving subnet 10.1.2.0.</span></span> <span data-ttu-id="ddd43-236">スーパーネッティングが実装されている場合は、サブネットの構築場所またはネットワークの種類 (ラボなど) がわかりません。</span><span class="sxs-lookup"><span data-stu-id="ddd43-236">If you implemented supernetting, you won't know where in the building the subnet is located or what type of network it is (for example, a lab).</span></span> <span data-ttu-id="ddd43-237">建物およびアップロードされたフロア位置情報のすべてのサブネットを定義した場合は、その区別を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-237">If you'd defined all the subnets for a building and uploaded floor location information, you'd be able to see that distinction.</span></span>

-   <span data-ttu-id="ddd43-238">Supernetted 住所が正しいこと、および不要なサブネットがキャッチされていないことを確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ddd43-238">It's important to ensure that the supernetted address is correct and isn't catching unwanted subnets.</span></span>

-   <span data-ttu-id="ddd43-239">192.168.0.0 をデータで検索するのは非常に一般的です。</span><span class="sxs-lookup"><span data-stu-id="ddd43-239">It's quite common to find 192.168.0.0 in data.</span></span> <span data-ttu-id="ddd43-240">多くの組織では、ユーザーが自宅にいることを示します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-240">For many organizations, this indicates that the user is at home.</span></span> <span data-ttu-id="ddd43-241">他のユーザーの場合、これは、サテライトオフィスの IP アドレススキームです。</span><span class="sxs-lookup"><span data-stu-id="ddd43-241">For others, this is the IP address scheme for a satellite office.</span></span> <span data-ttu-id="ddd43-242">組織でこの構成を使用しているオフィスがある場合は、 [共通のサブネット](quality-of-experience-review-guide.md#common-subnets)を使ってホームネットワークと内部ネットワークを区別することが難しいため、建物のファイルには含めないでください。</span><span class="sxs-lookup"><span data-stu-id="ddd43-242">If your organization does have offices that use this configuration, don't include it in your building file because it's difficult to distinguish between home and internal networks by using [common subnets](quality-of-experience-review-guide.md#common-subnets).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ddd43-243">ネットワーク範囲は、supernet を表すために使用できます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-243">The network range can be used to represent a supernet.</span></span> <span data-ttu-id="ddd43-244">新しくなったすべてのデータファイルアップロードで、重複範囲がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-244">All new building data file uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="ddd43-245">以前にビルドファイルをアップロードしたことがある場合は、現在のファイルをダウンロードしてもう一度アップロードし、重複を特定し、問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-245">If you've previously uploaded a building file, you should download the current file and upload it again to identify any overlaps and fix the issue.</span></span> <span data-ttu-id="ddd43-246">以前にアップロードされたファイルが重なっていると、サブネットとレポートの建物とのマッピングが間違っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-246">Any overlap in previously uploaded files might result in the wrong mappings of subnets to buildings in the reports.</span></span>

### <a name="vpn"></a><span data-ttu-id="ddd43-247">VPN</span><span class="sxs-lookup"><span data-stu-id="ddd43-247">VPN</span></span>

<span data-ttu-id="ddd43-248">CQD データのソースとなる Microsoft 365 または Office 365 に送信されるエクスペリエンス (QoE) データ— VPN フラグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-248">The quality of experience (QoE) data that clients send to Microsoft 365 or Office 365—which is where CQD data is sourced from—includes a VPN flag.</span></span> <span data-ttu-id="ddd43-249">CQD は、これを最初の VPN と第2の VPN のサイズとして表示します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-249">CQD will see this as the First VPN and Second VPN dimensions.</span></span> <span data-ttu-id="ddd43-250">ただし、このフラグは vpn ベンダーの Windows に依存し、VPN ネットワークアダプターが登録されていることがリモートアクセスアダプターであることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="ddd43-250">However, this flag relies on VPN vendors' reporting to Windows that the VPN network adapter registered is a Remote Access adapter.</span></span> <span data-ttu-id="ddd43-251">すべての VPN ベンダーがリモートアクセスアダプターを正しく登録しているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="ddd43-251">Not all VPN vendors properly register Remote Access adapters.</span></span> <span data-ttu-id="ddd43-252">このため、組み込みの VPN クエリフィルターを使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-252">Because of this, you might not be able to use the built-in VPN query filters.</span></span> <span data-ttu-id="ddd43-253">上で説明した VPN 列を使用して、VPN サブネットを正確にマークおよび識別します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-253">Use the VPN column discussed above to accurately mark and identify VPN subnets.</span></span> <span data-ttu-id="ddd43-254">また、レポートで簡単に識別できるように VPN ネットワークにラベルを付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ddd43-254">It is also good practice to label your VPN networks for easy identification in your reports.</span></span> <span data-ttu-id="ddd43-255">次に、VPN サブネットにラベルを付ける方法の2つの例を示します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-255">Below are two examples of how to label your VPN subnets:</span></span>

- <span data-ttu-id="ddd43-256">VPN サブネットの場合は、このフィールドに「VPN」と入力して、 **ネットワーク名** を定義します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-256">Define a **Network Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![ネットワーク名を使用した VPN を示す QCD レポートのスクリーンショット](media/qerguide-image-vpnnetworkname.png)

- <span data-ttu-id="ddd43-258">VPN サブネットの場合は、このフィールドに「VPN」と入力して **建物名** を定義します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-258">Define a **Building Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![建物名を使用した VPN を示す QCD レポートのスクリーンショット](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> <span data-ttu-id="ddd43-260">基盤となる接続がワイヤレスの場合、VPN 接続はネットワーク接続の種類を有線として misidentify ことがわかっています。</span><span class="sxs-lookup"><span data-stu-id="ddd43-260">VPN connections have been known to misidentify the network connection type as wired when the underlying connection is wireless.</span></span> <span data-ttu-id="ddd43-261">VPN 接続の品質を見ているときに、接続の種類が正確に識別されていると見なすことはできません。</span><span class="sxs-lookup"><span data-stu-id="ddd43-261">When looking at quality over VPN connections, you can't assume that the connection type has been accurately identified.</span></span>

## <a name="endpoint-data-file"></a><span data-ttu-id="ddd43-262">エンドポイントデータファイル</span><span class="sxs-lookup"><span data-stu-id="ddd43-262">Endpoint data file</span></span>

<span data-ttu-id="ddd43-263">もう1つの種類の CQD テナントデータファイルは、 **エンドポイント** データファイルです。</span><span class="sxs-lookup"><span data-stu-id="ddd43-263">The other type of CQD tenant data file is the **Endpoint** data file.</span></span> <span data-ttu-id="ddd43-264">列の値は、[通話記録の最初のクライアントエンドポイント名] または [第2のクライアントエンドポイント名] 列で使用され、エンドポイントの作成、モデル、または型の情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-264">The column values are used in the call record’s First Client Endpoint Name or Second Client Endpoint Name column to show Endpoint Make, Model, or Type information.</span></span> <span data-ttu-id="ddd43-265">アップロードするデータファイルの形式は、次の条件に従って、アップロード前に検証チェックに合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-265">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>

- <span data-ttu-id="ddd43-266">ファイルは、.tsv ファイル (列はタブで区切られます) または .csv ファイル (列はコンマで区切られます) のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-266">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="ddd43-267">データファイルの内容には、テーブル見出しは含まれません。</span><span class="sxs-lookup"><span data-stu-id="ddd43-267">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="ddd43-268">データファイルの最初の行は、"EndpointName" のような見出しラベルではなく、実際のデータである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-268">The first line of the data file is expected to be real data, not a header label like "EndpointName".</span></span>

- <span data-ttu-id="ddd43-269">7つの列はすべて、文字列データ型のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-269">All seven columns use the String data type only.</span></span> <span data-ttu-id="ddd43-270">使用できる最大文字数は64文字です。</span><span class="sxs-lookup"><span data-stu-id="ddd43-270">The maximum allowed length is 64 characters.</span></span>

- <span data-ttu-id="ddd43-271">データフィールドは空白にすることもできますが、タブまたはコンマで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-271">A data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="ddd43-272">空のデータフィールドでは、空の文字列値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-272">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="ddd43-273">EndpointName は一意である必要があります。そうでない場合、アップロードは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-273">EndpointName must be unique, otherwise the upload fails.</span></span> <span data-ttu-id="ddd43-274">重複している行が重複している場合、または2つの行に同じ EndpointName が含まれている場合は、競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-274">If there is a duplicate row or two rows that use the same EndpointName the conflict will  cause incorrect joining.</span></span>

- <span data-ttu-id="ddd43-275">EndpointLabel1、EndpointLabel2、EndpointLabel3 はカスタマイズ可能なラベルです。</span><span class="sxs-lookup"><span data-stu-id="ddd43-275">EndpointLabel1, EndpointLabel2, and EndpointLabel3 are customizable labels.</span></span> <span data-ttu-id="ddd43-276">空の文字列や値にすることができるのは、"IT 部門が指定した2018ノート Pc" または "Asset Tag 5678" などです。</span><span class="sxs-lookup"><span data-stu-id="ddd43-276">They can be empty Strings or values such as “IT Department designated 2018 Laptop” or “Asset Tag 5678”.</span></span>

- <span data-ttu-id="ddd43-277">各行には7つの列があり、列は次の順序である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-277">There must be seven columns for each row and the columns must be in the following order:</span></span>

  <span data-ttu-id="ddd43-278">**フィールドの順序:**</span><span class="sxs-lookup"><span data-stu-id="ddd43-278">**Field order:**</span></span>

  <span data-ttu-id="ddd43-279">EndpointName、EndpointMake、Endpointmake、Endpointmake、EndpointLabel1、EndpointLabel2、EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="ddd43-279">EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2,  EndpointLabel3</span></span>

  <span data-ttu-id="ddd43-280">**サンプルの行:**</span><span class="sxs-lookup"><span data-stu-id="ddd43-280">**Sample row:**</span></span>

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`


## <a name="update-a-building-file"></a><span data-ttu-id="ddd43-281">建物のファイルを更新する</span><span class="sxs-lookup"><span data-stu-id="ddd43-281">Update a building file</span></span>

<span data-ttu-id="ddd43-282">建物とサブネット情報を収集する場合、管理者は多くの場合、複数のイテレーションでビルドファイルをアップロードし、新しいサブネットとその建物情報が利用可能になったときにその作成情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-282">While gathering building and subnet information, administrators will often upload the building file in multiple iterations over time, adding new subnets and their building information as it becomes available.</span></span> <span data-ttu-id="ddd43-283">この問題が発生した場合は、建物のファイルを再アップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-283">When this occurs, you'll need to re-upload your building file.</span></span> <span data-ttu-id="ddd43-284">このプロセスは、前のセクションで説明した最初のアップロードのようなものです。次のセクションで説明するように、いくつかの例外があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-284">This process is like the initial upload as described in the previous section, with a few exceptions as noted in the following section.</span></span>

> [!Important]
> <span data-ttu-id="ddd43-285">一度に1つの建物ファイルのみをアクティブにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-285">Only one building file can be active at a time.</span></span> <span data-ttu-id="ddd43-286">複数のビルドファイルは累積的ではありません。</span><span class="sxs-lookup"><span data-stu-id="ddd43-286">Multiple building files aren't cumulative.</span></span>

## <a name="add-net-new-subnets"></a><span data-ttu-id="ddd43-287">ネット新しいサブネットを追加する</span><span class="sxs-lookup"><span data-stu-id="ddd43-287">Add net new subnets</span></span>

<span data-ttu-id="ddd43-288">元のネットワークトポロジの一部ではない、CQD にネット新しいサブネットを追加する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-288">There are times when you'll need to add net new subnets to CQD that weren't originally part of your network topology.</span></span> <span data-ttu-id="ddd43-289">ネット新しいサブネットを追加するには、CQD の **テナントデータアップロード** ページから次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ddd43-289">To add net new subnets, do the following from the **Tenant Data Upload** page in CQD:</span></span>

1.  <span data-ttu-id="ddd43-290">まだ最新の状態のコピーを持っていない場合は、元のファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ddd43-290">Download the original file, if you don't already have an up-to-date copy.</span></span>

1.  <span data-ttu-id="ddd43-291">CQD で現在のファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-291">Remove the current file in CQD.</span></span>

1.  <span data-ttu-id="ddd43-292">元の建物のファイルを編集して、ネット上の新しいサブネットが取得される前の少なくとも1日前に発生する終了日を指定します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-292">Edit the original building file and provide an end date that occurs at least one day before the net new subnets were acquired.</span></span>

1.  <span data-ttu-id="ddd43-293">元の建物ファイルにネット新しいサブネットを追加します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-293">Append the net new subnets to the original building file.</span></span>

1.  <span data-ttu-id="ddd43-294">新しく変更した建物ファイルをアップロードし、前の建物ファイルの終了後の1日の開始日を設定します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-294">Upload the newly modified building file, and set the start date for one day after the previous building file ends.</span></span>

## <a name="add-missing-subnets"></a><span data-ttu-id="ddd43-295">見つからないサブネットを追加する</span><span class="sxs-lookup"><span data-stu-id="ddd43-295">Add missing subnets</span></span>

<span data-ttu-id="ddd43-296">管理されたネットワークの建物情報をアップロードした後は、管理対象のすべてのネットワークに建物の関連付けを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-296">After you upload building information for managed networks, every managed network should have a building association.</span></span> <span data-ttu-id="ddd43-297">ただし、このような場合は常に問題になります。通常、いくつかのサブネットが失われます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-297">However, this won't always be the case; typically, a few subnets are missed.</span></span> <span data-ttu-id="ddd43-298">これらの見つからないネットワークを見つけるには、CQD の [ **エクスペリエンスレポートの品質** ] ページで、 **サブネット不足レポート** を確認します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-298">To find these missing networks, review the **Missing Subnet Report** on the **Quality of Experience Reports** page in CQD.</span></span> <span data-ttu-id="ddd43-299">これにより、作成データファイルに定義されていない10個以上のオーディオストリームを含むすべてのサブネットが表示され、外部としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-299">This presents all the subnets with 10 or more audio streams that aren't defined in the building data file and are being marked as outside.</span></span> <span data-ttu-id="ddd43-300">この一覧に管理されたネットワークがないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-300">Ensure that there are no managed networks in this list.</span></span> <span data-ttu-id="ddd43-301">サブネットが存在しない場合は、次の手順を使用して、元の建物データファイルを更新し、CQD に再アップロードします。</span><span class="sxs-lookup"><span data-stu-id="ddd43-301">If subnets are missing, use the following procedure to update the original building data file and re-upload it to CQD.</span></span>

1. <span data-ttu-id="ddd43-302">CQD の **テナントデータアップロード** ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-302">Go to the **Tenant Data Upload** page in CQD.</span></span>

1. <span data-ttu-id="ddd43-303">まだ最新の状態のコピーを持っていない場合は、元のファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ddd43-303">Download the original file, if you don't already have an up-to-date copy.</span></span>

1. <span data-ttu-id="ddd43-304">CQD で現在のファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-304">Remove the current file in CQD.</span></span>

1. <span data-ttu-id="ddd43-305">新しいサブネットを元のファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-305">Append the new subnets to the original file.</span></span>

1. <span data-ttu-id="ddd43-306">建物のファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="ddd43-306">Upload the building file.</span></span> <span data-ttu-id="ddd43-307">CQD が履歴データを処理するためには、少なくとも8か月前に開始日を設定しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-307">Be sure to set the start date to at least eight months prior so that CQD will process historical data.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="ddd43-308">組織のテナントデータのみを表示するようにレポートをフィルター処理するには、テナント ID を **第2のテナント id** のクエリフィルターとしてこのレポートに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-308">You'll need to add your tenant ID as a query filter for **Second Tenant ID** to this report to filter the report to view only your organization's tenant data.</span></span> <span data-ttu-id="ddd43-309">そうしないと、レポートにフェデレーションサブネットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-309">Otherwise, the report will show federated subnets.</span></span>

> [!NOTE] 
> <span data-ttu-id="ddd43-310">月単位のレポートフィルターは、現在の月に合わせて調整してください。</span><span class="sxs-lookup"><span data-stu-id="ddd43-310">Be sure to adjust the Month Year report filter to the current month.</span></span> <span data-ttu-id="ddd43-311">[ **編集** ] を選択し、 **month Year** レポートフィルターを調整して、新しい既定の月を保存します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-311">Select **Edit** , and adjust the **Month Year** report filter to save the new default month.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ddd43-312">関連項目</span><span class="sxs-lookup"><span data-stu-id="ddd43-312">Related topics</span></span>

[<span data-ttu-id="ddd43-313">CQD 用の建築地図を作成する</span><span class="sxs-lookup"><span data-stu-id="ddd43-313">Create a building map for CQD</span></span>](CQD-building-mapping.md)

[<span data-ttu-id="ddd43-314">Teams の通話品質を向上させて監視する</span><span class="sxs-lookup"><span data-stu-id="ddd43-314">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="ddd43-315">CQD とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="ddd43-315">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="ddd43-316">通話品質ダッシュボード (CQD) を設定する</span><span class="sxs-lookup"><span data-stu-id="ddd43-316">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="ddd43-317">CQD データとレポート</span><span class="sxs-lookup"><span data-stu-id="ddd43-317">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="ddd43-318">CQD を使用して通話と会議の品質を管理する</span><span class="sxs-lookup"><span data-stu-id="ddd43-318">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="ddd43-319">CQD で使用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="ddd43-319">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="ddd43-320">CQD でのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="ddd43-320">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="ddd43-321">Power BI を使用して CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="ddd43-321">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
