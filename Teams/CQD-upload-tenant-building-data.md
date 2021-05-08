---
title: アップロード品質ダッシュボード (CQD) でテナントを管理し、データを構築する
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
description: 通話品質ダッシュボード (CQD) でテナントをアップロードし、データを構築する方法について学習します。
ms.openlocfilehash: 7a1f6de78e01a8988317aa99aae917aa0018e19a
ms.sourcegitcommit: 7e673b88346e07f7c777710437b19d257ccecb1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2021
ms.locfileid: "50067142"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a><span data-ttu-id="e3952-103">アップロード品質ダッシュボード (CQD) でテナントを管理し、データを構築する</span><span class="sxs-lookup"><span data-stu-id="e3952-103">Upload tenant and building data in Call Quality Dashboard (CQD)</span></span>


<span data-ttu-id="e3952-104">通話品質ダッシュボード (CQD) を利用するには、テナントをアップロードしてデータを構築することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e3952-104">To get the most out of Call Quality Dashboard (CQD), we recommend that you upload your tenant and building data.</span></span> <span data-ttu-id="e3952-105">テナント データ ファイルには、Building と Endpoint の 2[種類](#upload-building-data-file)[があります](#endpoint-data-file)。</span><span class="sxs-lookup"><span data-stu-id="e3952-105">There are 2 types of tenant data files, [Building](#upload-building-data-file) and [Endpoint](#endpoint-data-file).</span></span>

<span data-ttu-id="e3952-106">サンプル テナント データ テンプレートは、 からダウンロード [できます](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="e3952-106">You can download a sample tenant data template [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).</span></span> <span data-ttu-id="e3952-107">マッピングの構築に関するヘルプについては [、「CQD の建物マップを作成する」を参照してください](CQD-building-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="e3952-107">For help with building mapping, read [Create a building map for CQD](CQD-building-mapping.md).</span></span>

<span data-ttu-id="e3952-108">CQD サマリー レポート ダッシュボードで、[CQD 設定] メニュー (CQD の上部にある歯車アイコン **)** から [テナント データ アップロード] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3952-108">From the CQD Summary Reports dashboard, select **Tenant Data Upload** from the CQD **Settings** menu (a gear icon at the top of CQD).</span></span> <span data-ttu-id="e3952-109">ここから、管理者は、IP アドレスと地理的情報のマッピング、各ワイヤレス アクセス ポイントとその MAC アドレスのマッピングなど、組織の建物とエンドポイントの情報をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="e3952-109">From here, admins can upload their organization's building and endpoint information, such as mapping of IP addresses and geographical information, mapping each wireless access point and its MAC address, etc.</span></span>

1. <span data-ttu-id="e3952-110">(Teams 管理センターまたは ) から CQD を開き、右上隅にある歯車アイコンを選択し、[概要レポート] ページから [テナント データ [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) **アップロード]** を **選択** します。</span><span class="sxs-lookup"><span data-stu-id="e3952-110">Open CQD (from the Teams admin center, or at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)), then select the gear icon in the upper-right corner and choose **Tenant Data Upload** from the **Summary Reports** page.</span></span>

   ![データのアップロード中に表示されるダイアログ ボックスのスクリーンショット](media/qerguide-image-tenantdataupload.png)
    
2. <span data-ttu-id="e3952-112">または、初めて CQD を訪問する場合は、建物のデータをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-112">Alternatively, if this is your first time visiting CQD, you'll be asked to upload building data.</span></span> <span data-ttu-id="e3952-113">[今すぐ **アップロード] を** 選択すると、[テナント データ] ページ **アップロード** できます。</span><span class="sxs-lookup"><span data-stu-id="e3952-113">You can select **Upload Now** to quickly navigate to the **Tenant Data Upload** page.</span></span>

   ![建物のデータをアップロードするユーザーに通知するバナーのスクリーンショット](media/qerguide-image-buildingdatauploadbanner.png)

3. <span data-ttu-id="e3952-115">[Tenant **Data アップロード]** ページで、[参照]**を選択して** データ ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3952-115">On the **Tenant Data Upload** page, select **Browse** to choose a data file.</span></span>

4. <span data-ttu-id="e3952-116">データ ファイルを選択した後、[開始日 **] を指定** し、必要に応じて終了日を指定します。</span><span class="sxs-lookup"><span data-stu-id="e3952-116">After selecting a data file, specify **Start date** and, optionally, specify an end date.</span></span>

5. <span data-ttu-id="e3952-117">[開始日]**を選択した\*\*\*\*後、アップロード** を選択して CQD にファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="e3952-117">After selecting **Start date**, select **Upload** to upload the file to CQD.</span></span> <br><br><span data-ttu-id="e3952-118">ファイルがアップロードされる前に、ファイルが検証されます。</span><span class="sxs-lookup"><span data-stu-id="e3952-118">Before the file is uploaded, it's validated.</span></span> <span data-ttu-id="e3952-119">検証に失敗した場合は、ファイルを修正する必要があるというエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3952-119">If validation fails, an error message is displayed requesting that you correct the file.</span></span> <span data-ttu-id="e3952-120">次の図は、データ ファイル内の列数が正しくない場合に発生するエラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="e3952-120">The following figure shows an error occurring when the number of columns in the data file is incorrect.</span></span>

   ![建物データのアップロード エラーを表示するダイアログ ボックスの例](media/qerguide-image-buildingdatauploaderror.png)
 
6. <span data-ttu-id="e3952-122">検証中にエラーが発生しない場合、ファイルのアップロードは成功します。</span><span class="sxs-lookup"><span data-stu-id="e3952-122">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="e3952-123">アップロードしたデータ ファイルは、[ **マイ アップロード** ] テーブルに表示されます。このテーブルには、現在のテナントのアップロード済みファイルの完全な一覧がページの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3952-123">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>

> [!NOTE]
> <span data-ttu-id="e3952-124">ファイルの作成処理が完了するために最大 4 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-124">It can take up to four hours to finish processing the building file.</span></span> <br><br> <span data-ttu-id="e3952-125">既に建物ファイルをアップロードし、欠落または除外されている可能性があるサブネットを追加する必要がある場合は、新しいサブネットを追加して元のファイルを変更し、現在のファイルを削除し、新しく編集したファイルを再アップロードします。</span><span class="sxs-lookup"><span data-stu-id="e3952-125">If you've already uploaded a building file and need to add subnets that might have been missed or excluded, modify the original file by adding the new subnets, remove the current file, and re-upload the newly edited file.</span></span> <span data-ttu-id="e3952-126">CQD には、アクティブな建物データ ファイルを 1 つしか作成できます。</span><span class="sxs-lookup"><span data-stu-id="e3952-126">There can be only one active building data file in CQD.</span></span> 


## <a name="upload-building-data-file"></a><span data-ttu-id="e3952-127">アップロードファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="e3952-127">Upload building data file</span></span>

<span data-ttu-id="e3952-128">CQD のテナント データ ファイルの最初の種類は、 **データ ファイルの作成** です。</span><span class="sxs-lookup"><span data-stu-id="e3952-128">The first type of tenant data file in CQD is the **Building** data file.</span></span> <span data-ttu-id="e3952-129">[サブネット] 列は、[Network+NetworkRange] 列を展開し、[サブネット] 列を呼び出しレコードの [最初のサブネット] 列または [2 つ目のサブネット] 列に結合して、建物、市区町場、国、または地域の情報を表示することで派生します。</span><span class="sxs-lookup"><span data-stu-id="e3952-129">The Subnet column is derived by expanding the Network+NetworkRange column, then joining the Subnet column to the call record’s First Subnet or Second Subnet column to show Building, City, Country, or Region information.</span></span> <span data-ttu-id="e3952-130">アップロードするデータ ファイルの形式は、アップロード前に検証チェックに合格するために、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-130">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>
  
- <span data-ttu-id="e3952-131">ファイルは 、.tsv ファイル (列は TAB で区切られます) または .csv ファイル (列はコンマで区切られています) のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-131">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="e3952-132">データ ファイルには、テーブルの見出し行は含めされません。</span><span class="sxs-lookup"><span data-stu-id="e3952-132">The data file doesn't include a table header row.</span></span> <span data-ttu-id="e3952-133">データ ファイルの最初の行は、"ネットワーク" のようなヘッダー ラベルではなく、実際のデータである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-133">The first line of the data file is expected to be real data, not header labels like "Network".</span></span>

- <span data-ttu-id="e3952-134">ファイル内のデータ型は、String、Integer、または Boolean のみです。</span><span class="sxs-lookup"><span data-stu-id="e3952-134">Data types in the file can only be String, Integer, or Boolean.</span></span> <span data-ttu-id="e3952-135">整数型の場合、値は数値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-135">For the  Integer data type, the value must be a numeric value.</span></span> <span data-ttu-id="e3952-136">ブール値は 0 または 1 のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-136">Boolean values must be either 0 or 1.</span></span>

- <span data-ttu-id="e3952-137">列で文字列型を使用する場合、データ フィールドは空にできますが、タブまたはコンマで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-137">If a column uses the String data type, a data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="e3952-138">空のデータ フィールドでは、空の文字列値が割り当てらされます。</span><span class="sxs-lookup"><span data-stu-id="e3952-138">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="e3952-139">テナント データ ファイルごとに 1,000,000 行の拡張制限があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-139">There is a 1,000,000 expanded row limit per tenant data file.</span></span>

- <span data-ttu-id="e3952-140">行ごとに 15 列が必要です。各列には適切なデータ型が必要です。列は次の表に示す順序 (コンマまたはタブ区切り) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-140">There must be 15 columns for each row, each column must have the appropriate data type, and the columns must be in the order listed in the following table (comma or tab delimited):</span></span>

  <span data-ttu-id="e3952-141">**データ ファイル形式の構築**</span><span class="sxs-lookup"><span data-stu-id="e3952-141">**Building data file format**</span></span>
  
  | <span data-ttu-id="e3952-142">列名</span><span class="sxs-lookup"><span data-stu-id="e3952-142">Column name</span></span>        | <span data-ttu-id="e3952-143">データの種類</span><span class="sxs-lookup"><span data-stu-id="e3952-143">Data type</span></span> | <span data-ttu-id="e3952-144">例</span><span class="sxs-lookup"><span data-stu-id="e3952-144">Example</span></span>                   | <span data-ttu-id="e3952-145">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="e3952-145">Guidance</span></span>              |
  |--------------------|-----------|---------------------------|-----------------------|
  | <span data-ttu-id="e3952-146">NetworkIP</span><span class="sxs-lookup"><span data-stu-id="e3952-146">NetworkIP</span></span>          | <span data-ttu-id="e3952-147">文字列</span><span class="sxs-lookup"><span data-stu-id="e3952-147">String</span></span>    | <span data-ttu-id="e3952-148">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="e3952-148">192.168.1.0</span></span>               | <span data-ttu-id="e3952-149">必須</span><span class="sxs-lookup"><span data-stu-id="e3952-149">Required</span></span>              |
  | <span data-ttu-id="e3952-150">NetworkName</span><span class="sxs-lookup"><span data-stu-id="e3952-150">NetworkName</span></span>        | <span data-ttu-id="e3952-151">文字列</span><span class="sxs-lookup"><span data-stu-id="e3952-151">String</span></span>    | <span data-ttu-id="e3952-152">USA/Seattle/SEATTLE-SEA-1</span><span class="sxs-lookup"><span data-stu-id="e3952-152">USA/Seattle/SEATTLE-SEA-1</span></span> | <span data-ttu-id="e3952-153">必須<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e3952-153">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="e3952-154">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="e3952-154">NetworkRange</span></span>       | <span data-ttu-id="e3952-155">数値</span><span class="sxs-lookup"><span data-stu-id="e3952-155">Number</span></span>    | <span data-ttu-id="e3952-156">26</span><span class="sxs-lookup"><span data-stu-id="e3952-156">26</span></span>                        | <span data-ttu-id="e3952-157">必須</span><span class="sxs-lookup"><span data-stu-id="e3952-157">Required</span></span>              |
  | <span data-ttu-id="e3952-158">BuildingName</span><span class="sxs-lookup"><span data-stu-id="e3952-158">BuildingName</span></span>       | <span data-ttu-id="e3952-159">文字列</span><span class="sxs-lookup"><span data-stu-id="e3952-159">String</span></span>    | <span data-ttu-id="e3952-160">SEATTLE-SEA-1</span><span class="sxs-lookup"><span data-stu-id="e3952-160">SEATTLE-SEA-1</span></span>             | <span data-ttu-id="e3952-161">必須<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e3952-161">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="e3952-162">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="e3952-162">OwnershipType</span></span>      | <span data-ttu-id="e3952-163">文字列</span><span class="sxs-lookup"><span data-stu-id="e3952-163">String</span></span>    | <span data-ttu-id="e3952-164">Contoso</span><span class="sxs-lookup"><span data-stu-id="e3952-164">Contoso</span></span>                   | <span data-ttu-id="e3952-165">省略可能</span><span class="sxs-lookup"><span data-stu-id="e3952-165">Optional</span></span>              |
  | <span data-ttu-id="e3952-166">BuildingType</span><span class="sxs-lookup"><span data-stu-id="e3952-166">BuildingType</span></span>       | <span data-ttu-id="e3952-167">文字列</span><span class="sxs-lookup"><span data-stu-id="e3952-167">String</span></span>    | <span data-ttu-id="e3952-168">IT 終了</span><span class="sxs-lookup"><span data-stu-id="e3952-168">IT Termination</span></span>            | <span data-ttu-id="e3952-169">省略可能</span><span class="sxs-lookup"><span data-stu-id="e3952-169">Optional</span></span>              |
  | <span data-ttu-id="e3952-170">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="e3952-170">BuildingOfficeType</span></span> | <span data-ttu-id="e3952-171">文字列</span><span class="sxs-lookup"><span data-stu-id="e3952-171">String</span></span>    | <span data-ttu-id="e3952-172">エンジニアリング</span><span class="sxs-lookup"><span data-stu-id="e3952-172">Engineering</span></span>               | <span data-ttu-id="e3952-173">省略可能</span><span class="sxs-lookup"><span data-stu-id="e3952-173">Optional</span></span>              |
  | <span data-ttu-id="e3952-174">市区町村</span><span class="sxs-lookup"><span data-stu-id="e3952-174">City</span></span>               | <span data-ttu-id="e3952-175">文字列</span><span class="sxs-lookup"><span data-stu-id="e3952-175">String</span></span>    | <span data-ttu-id="e3952-176">調布市調布ヶ丘</span><span class="sxs-lookup"><span data-stu-id="e3952-176">Seattle</span></span>                   | <span data-ttu-id="e3952-177">推奨</span><span class="sxs-lookup"><span data-stu-id="e3952-177">Recommended</span></span>           |
  | <span data-ttu-id="e3952-178">ZipCode</span><span class="sxs-lookup"><span data-stu-id="e3952-178">ZipCode</span></span>            | <span data-ttu-id="e3952-179">文字列</span><span class="sxs-lookup"><span data-stu-id="e3952-179">String</span></span>    | <span data-ttu-id="e3952-180">98001</span><span class="sxs-lookup"><span data-stu-id="e3952-180">98001</span></span>                     | <span data-ttu-id="e3952-181">推奨</span><span class="sxs-lookup"><span data-stu-id="e3952-181">Recommended</span></span>           |
  | <span data-ttu-id="e3952-182">国</span><span class="sxs-lookup"><span data-stu-id="e3952-182">Country</span></span>            | <span data-ttu-id="e3952-183">文字列</span><span class="sxs-lookup"><span data-stu-id="e3952-183">String</span></span>    | <span data-ttu-id="e3952-184">米国</span><span class="sxs-lookup"><span data-stu-id="e3952-184">US</span></span>                        | <span data-ttu-id="e3952-185">推奨</span><span class="sxs-lookup"><span data-stu-id="e3952-185">Recommended</span></span>           |
  | <span data-ttu-id="e3952-186">都道府県</span><span class="sxs-lookup"><span data-stu-id="e3952-186">State</span></span>              | <span data-ttu-id="e3952-187">文字列</span><span class="sxs-lookup"><span data-stu-id="e3952-187">String</span></span>    | <span data-ttu-id="e3952-188">WA</span><span class="sxs-lookup"><span data-stu-id="e3952-188">WA</span></span>                        | <span data-ttu-id="e3952-189">推奨</span><span class="sxs-lookup"><span data-stu-id="e3952-189">Recommended</span></span>           |
  | <span data-ttu-id="e3952-190">Region</span><span class="sxs-lookup"><span data-stu-id="e3952-190">Region</span></span>             | <span data-ttu-id="e3952-191">文字列</span><span class="sxs-lookup"><span data-stu-id="e3952-191">String</span></span>    | <span data-ttu-id="e3952-192">MSUS</span><span class="sxs-lookup"><span data-stu-id="e3952-192">MSUS</span></span>                      | <span data-ttu-id="e3952-193">推奨</span><span class="sxs-lookup"><span data-stu-id="e3952-193">Recommended</span></span>           |
  | <span data-ttu-id="e3952-194">InsideCorp<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e3952-194">InsideCorp<sup>2</sup></span></span>         | <span data-ttu-id="e3952-195">ブール</span><span class="sxs-lookup"><span data-stu-id="e3952-195">Bool</span></span>      | <span data-ttu-id="e3952-196">1</span><span class="sxs-lookup"><span data-stu-id="e3952-196">1</span></span>             | <span data-ttu-id="e3952-197">必須</span><span class="sxs-lookup"><span data-stu-id="e3952-197">Required</span></span>              |
  | <span data-ttu-id="e3952-198">ExpressRoute<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e3952-198">ExpressRoute<sup>3</sup></span></span>       | <span data-ttu-id="e3952-199">ブール</span><span class="sxs-lookup"><span data-stu-id="e3952-199">Bool</span></span>      | <span data-ttu-id="e3952-200">0</span><span class="sxs-lookup"><span data-stu-id="e3952-200">0</span></span>             | <span data-ttu-id="e3952-201">必須</span><span class="sxs-lookup"><span data-stu-id="e3952-201">Required</span></span>              |
  | <span data-ttu-id="e3952-202">VPN</span><span class="sxs-lookup"><span data-stu-id="e3952-202">VPN</span></span>                | <span data-ttu-id="e3952-203">ブール</span><span class="sxs-lookup"><span data-stu-id="e3952-203">Bool</span></span>      | <span data-ttu-id="e3952-204">0</span><span class="sxs-lookup"><span data-stu-id="e3952-204">0</span></span>                         | <span data-ttu-id="e3952-205">省略可能</span><span class="sxs-lookup"><span data-stu-id="e3952-205">Optional</span></span>              |

  <span data-ttu-id="e3952-206"><sup>1</sup> CQD では必須ではありませんが、テンプレートは [Building] と [Network name] を表示するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="e3952-206"><sup>1</sup> While not required by CQD, the templates are configured to display Building and Network name.</span></span>

  <span data-ttu-id="e3952-207"><sup>2</sup> この設定は、サブネットが企業ネットワーク内にあるかどうかを反映するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3952-207"><sup>2</sup> This setting can be used to reflect whether or not the subnet is inside the corporate network.</span></span> <span data-ttu-id="e3952-208">その他の目的で使用状況をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="e3952-208">You can customize usage for other purposes.</span></span>

  <span data-ttu-id="e3952-209"><sup>3</sup> この設定は、ネットワークが Azure ExpressRoute を使用するかどうかを反映するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3952-209"><sup>3</sup> This setting can be used to reflect whether or not the network uses Azure ExpressRoute.</span></span> <span data-ttu-id="e3952-210">その他の目的で使用状況をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="e3952-210">You can customize usage for other purposes.</span></span>  

  <span data-ttu-id="e3952-211">**サンプル行:**</span><span class="sxs-lookup"><span data-stu-id="e3952-211">**Sample row:**</span></span>

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> <span data-ttu-id="e3952-212">ネットワーク範囲は、スーパーネット (複数のサブネットと 1 つのルーティング プレフィックスの組み合わせ) を表す場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3952-212">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="e3952-213">新しい建物のアップロードはすべて、重複する範囲がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="e3952-213">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="e3952-214">以前に建物のファイルをアップロードした場合は、現在のファイルをダウンロードし、再アップロードして重複を特定し、問題を修正してから、もう一度アップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-214">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="e3952-215">以前にアップロードしたファイルの重複により、レポート内の建物へのサブネットのマッピングが間違っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-215">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="e3952-216">特定の VPN 実装では、サブネット情報が正確に報告されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-216">Certain VPN implementations do not accurately report the subnet information.</span></span> 
>
> <span data-ttu-id="e3952-217">VPN 列は省略可能で、既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="e3952-217">The VPN column is optional and will default to 0.</span></span> <span data-ttu-id="e3952-218">VPN 列の値が 1 に設定されている場合、その行で表されるサブネットは、サブネット内のすべての IP アドレスに一致するために完全に展開されます。</span><span class="sxs-lookup"><span data-stu-id="e3952-218">If the VPN column’s value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span> <span data-ttu-id="e3952-219">これらのサブネットを完全に拡張すると、データの構築に関連するクエリのクエリ時間に悪影響を与えるので、VPN サブネットに対して、この設定は少し注意して使用してください。</span><span class="sxs-lookup"><span data-stu-id="e3952-219">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span> <span data-ttu-id="e3952-220">サブネットの拡張によって拡張行の制限が 1,000,000 を超えた場合、建物ファイルは受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="e3952-220">If the expansion of the subnet results in the expansion row limit of 1,000,000 being exceeded, the building file will not be accepted.</span></span>


### <a name="supernetting"></a><span data-ttu-id="e3952-221">スーパーネット</span><span class="sxs-lookup"><span data-stu-id="e3952-221">Supernetting</span></span>

<span data-ttu-id="e3952-222">各サブネットを定義する代Inter-Domain、一般的にクラスレス ルーティング (CIDR) と呼ばれるスーパーネットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3952-222">You can use supernetting, commonly called Classless Inter-Domain Routing (CIDR,) in place of defining each subnet.</span></span> <span data-ttu-id="e3952-223">スーパー *ネットは、1* つのルーティング プレフィックスを共有する複数のサブネットの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="e3952-223">A *supernet* is a combination of several subnets that share a single routing prefix.</span></span> <span data-ttu-id="e3952-224">サブネットごとにエントリを追加する代わりに、スーパーネット アドレスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3952-224">Instead of adding an entry for each subnet, you can use the supernetted address.</span></span> <span data-ttu-id="e3952-225">スーパーネットはサポートされますが、使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="e3952-225">Supernetting is supported, but we don't recommend using it.</span></span>

<span data-ttu-id="e3952-226">たとえば、Contoso のマーケティングの建物は、次のサブネットで構成されています。</span><span class="sxs-lookup"><span data-stu-id="e3952-226">For example, Contoso's marketing building is made up of the subnets below:</span></span>

-   <span data-ttu-id="e3952-227">10.1.0.0/24 - 1 階</span><span class="sxs-lookup"><span data-stu-id="e3952-227">10.1.0.0/24—first floor</span></span>
-   <span data-ttu-id="e3952-228">10.1.1.0/24 — 2 階</span><span class="sxs-lookup"><span data-stu-id="e3952-228">10.1.1.0/24—second floor</span></span>
-   <span data-ttu-id="e3952-229">10.1.2.0/24 - 3 階</span><span class="sxs-lookup"><span data-stu-id="e3952-229">10.1.2.0/24—third floor</span></span>
-   <span data-ttu-id="e3952-230">10.1.3.0/24 - 4 階</span><span class="sxs-lookup"><span data-stu-id="e3952-230">10.1.3.0/24—fourth floor</span></span>

<span data-ttu-id="e3952-231">サブネットごとにエントリを追加する代わりに、スーパーネット アドレス (この例では 10.1.0.0/22) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3952-231">Instead of adding an entry for each subnet, you can use the supernetted address—in this example, 10.1.0.0/22.</span></span>

-   <span data-ttu-id="e3952-232">Network = 10.1.0.0</span><span class="sxs-lookup"><span data-stu-id="e3952-232">Network = 10.1.0.0</span></span>
-   <span data-ttu-id="e3952-233">ネットワーク範囲 = 22</span><span class="sxs-lookup"><span data-stu-id="e3952-233">Network Range = 22</span></span>

<span data-ttu-id="e3952-234">スーパーネットを実装する前に考慮すべき点を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e3952-234">Here are a few things to consider before you implement supernetting:</span></span>

-   <span data-ttu-id="e3952-235">スーパーネットは、8 ビットから 28 ビットマスクのサブネット マッピングでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3952-235">Supernetting can only be used in a subnet mapping with 8-bit to 28-bit mask.</span></span>

-   <span data-ttu-id="e3952-236">スーパーネット処理は、前もって行う時間は少なめですが、データのリッチ度を減らすコストがかかります。</span><span class="sxs-lookup"><span data-stu-id="e3952-236">Supernetting takes less time up front, but it comes at the cost of reducing the richness of your data.</span></span> <span data-ttu-id="e3952-237">たとえば、サブネット 10.1.2.0 に関する品質の問題が発生したとします。</span><span class="sxs-lookup"><span data-stu-id="e3952-237">Let's say there's a quality problem involving subnet 10.1.2.0.</span></span> <span data-ttu-id="e3952-238">スーパーネットを実装した場合、建物のどこにサブネットがあるのか、ネットワークの種類 (ラボなど) はわかりません。</span><span class="sxs-lookup"><span data-stu-id="e3952-238">If you implemented supernetting, you won't know where in the building the subnet is located or what type of network it is (for example, a lab).</span></span> <span data-ttu-id="e3952-239">ビルのすべてのサブネットを定義し、フロアの場所情報をアップロードした場合は、その違いを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e3952-239">If you'd defined all the subnets for a building and uploaded floor location information, you'd be able to see that distinction.</span></span>

-   <span data-ttu-id="e3952-240">スーパーネット アドレスが正しく、不要なサブネットをキャッチしない必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-240">It's important to ensure that the supernetted address is correct and isn't catching unwanted subnets.</span></span>

-   <span data-ttu-id="e3952-241">データで 192.168.0.0 を見つけるのは非常に一般的です。</span><span class="sxs-lookup"><span data-stu-id="e3952-241">It's quite common to find 192.168.0.0 in data.</span></span> <span data-ttu-id="e3952-242">多くの組織では、これはユーザーが自宅にいを示しています。</span><span class="sxs-lookup"><span data-stu-id="e3952-242">For many organizations, this indicates that the user is at home.</span></span> <span data-ttu-id="e3952-243">他のユーザーの場合、これは衛星オフィスの IP アドレス スキームです。</span><span class="sxs-lookup"><span data-stu-id="e3952-243">For others, this is the IP address scheme for a satellite office.</span></span> <span data-ttu-id="e3952-244">組織にこの構成を使用するオフィスがある場合は、一般的なサブネット を使用してホーム ネットワークと内部ネットワークを区別するのが難しいため、建物ファイルに含め [ないことです](quality-of-experience-review-guide.md#common-subnets)。</span><span class="sxs-lookup"><span data-stu-id="e3952-244">If your organization does have offices that use this configuration, don't include it in your building file because it's difficult to distinguish between home and internal networks by using [common subnets](quality-of-experience-review-guide.md#common-subnets).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e3952-245">ネットワーク範囲は、スーパーネットを表す場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3952-245">The network range can be used to represent a supernet.</span></span> <span data-ttu-id="e3952-246">新しい建物データ ファイルのアップロードはすべて、重複する範囲がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="e3952-246">All new building data file uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="e3952-247">以前に建物ファイルをアップロードした場合は、現在のファイルをダウンロードし、もう一度アップロードして重複を特定し、問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-247">If you've previously uploaded a building file, you should download the current file and upload it again to identify any overlaps and fix the issue.</span></span> <span data-ttu-id="e3952-248">以前にアップロードしたファイルの重複により、レポート内の建物へのサブネットのマッピングが間違っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-248">Any overlap in previously uploaded files might result in the wrong mappings of subnets to buildings in the reports.</span></span>

### <a name="vpn"></a><span data-ttu-id="e3952-249">VPN</span><span class="sxs-lookup"><span data-stu-id="e3952-249">VPN</span></span>

<span data-ttu-id="e3952-250">クライアントが Microsoft 365 または Office 365 に送信するエクスペリエンスの品質 (QoE) データ (CQD データの送信元) には、VPN フラグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3952-250">The quality of experience (QoE) data that clients send to Microsoft 365 or Office 365—which is where CQD data is sourced from—includes a VPN flag.</span></span> <span data-ttu-id="e3952-251">CQD では、これが第 1 VPN および第 2 VPN ディメンションとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3952-251">CQD will see this as the First VPN and Second VPN dimensions.</span></span> <span data-ttu-id="e3952-252">ただし、このフラグは、登録されている VPN ネットワーク アダプターがリモート アクセス アダプター Windows VPN ベンダーのレポートに依存します。</span><span class="sxs-lookup"><span data-stu-id="e3952-252">However, this flag relies on VPN vendors' reporting to Windows that the VPN network adapter registered is a Remote Access adapter.</span></span> <span data-ttu-id="e3952-253">すべての VPN ベンダーがリモート アクセス アダプターを正しく登録しているのではありません。</span><span class="sxs-lookup"><span data-stu-id="e3952-253">Not all VPN vendors properly register Remote Access adapters.</span></span> <span data-ttu-id="e3952-254">この理由から、組み込みの VPN クエリ フィルターを使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-254">Because of this, you might not be able to use the built-in VPN query filters.</span></span> <span data-ttu-id="e3952-255">VPN サブネットを正確にマークして識別するには、上記の VPN 列を使用します。</span><span class="sxs-lookup"><span data-stu-id="e3952-255">Use the VPN column discussed above to accurately mark and identify VPN subnets.</span></span> <span data-ttu-id="e3952-256">また、VPN ネットワークにラベルを付け、レポートの識別を容易に行うのも良い方法です。</span><span class="sxs-lookup"><span data-stu-id="e3952-256">It is also good practice to label your VPN networks for easy identification in your reports.</span></span> <span data-ttu-id="e3952-257">VPN サブネットにラベルを付けるには、次の 2 つの例を示します。</span><span class="sxs-lookup"><span data-stu-id="e3952-257">Below are two examples of how to label your VPN subnets:</span></span>

- <span data-ttu-id="e3952-258">VPN サブネット **のこのフィールドに** 「VPN」と入力して、ネットワーク名を定義します。</span><span class="sxs-lookup"><span data-stu-id="e3952-258">Define a **Network Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![ネットワーク名を使用した VPN を示す QCD レポートのスクリーンショット](media/qerguide-image-vpnnetworkname.png)

- <span data-ttu-id="e3952-260">VPN サブネット **のこのフィールドに** 「VPN」と入力して、ビル名を定義します。</span><span class="sxs-lookup"><span data-stu-id="e3952-260">Define a **Building Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![建物名を使用した VPN を示す QCD レポートのスクリーンショット](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> <span data-ttu-id="e3952-262">VPN 接続は、基になる接続がワイヤレスのときに、ネットワーク接続の種類を有線と誤って確認することが知られています。</span><span class="sxs-lookup"><span data-stu-id="e3952-262">VPN connections have been known to misidentify the network connection type as wired when the underlying connection is wireless.</span></span> <span data-ttu-id="e3952-263">VPN 接続を使用した品質を確認する場合、接続の種類が正確に識別されたと想定できません。</span><span class="sxs-lookup"><span data-stu-id="e3952-263">When looking at quality over VPN connections, you can't assume that the connection type has been accurately identified.</span></span>

## <a name="endpoint-data-file"></a><span data-ttu-id="e3952-264">エンドポイント データ ファイル</span><span class="sxs-lookup"><span data-stu-id="e3952-264">Endpoint data file</span></span>

<span data-ttu-id="e3952-265">もう 1 つの種類の CQD テナント データ ファイルは **、エンドポイント データ ファイル** です。</span><span class="sxs-lookup"><span data-stu-id="e3952-265">The other type of CQD tenant data file is the **Endpoint** data file.</span></span> <span data-ttu-id="e3952-266">列の値は、呼び出しレコードの [最初のクライアント エンドポイント名] 列または [2 番目のクライアント エンドポイント名] 列で、エンドポイントの作成、モデル、または種類の情報を表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3952-266">The column values are used in the call record’s First Client Endpoint Name or Second Client Endpoint Name column to show Endpoint Make, Model, or Type information.</span></span> <span data-ttu-id="e3952-267">アップロードするデータ ファイルの形式は、アップロード前に検証チェックに合格するために、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-267">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>

- <span data-ttu-id="e3952-268">ファイルは 、.tsv ファイル (列は TAB で区切られます) または .csv ファイル (列はコンマで区切られています) のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-268">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="e3952-269">データ ファイルの内容には、テーブル ヘッダーは含めされません。</span><span class="sxs-lookup"><span data-stu-id="e3952-269">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="e3952-270">データ ファイルの最初の行は、"EndpointName" のようなヘッダー ラベルではなく、実際のデータである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-270">The first line of the data file is expected to be real data, not a header label like "EndpointName".</span></span>

- <span data-ttu-id="e3952-271">7 つの列はすべて、String データ型のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="e3952-271">All seven columns use the String data type only.</span></span> <span data-ttu-id="e3952-272">最大許容長は 64 文字です。</span><span class="sxs-lookup"><span data-stu-id="e3952-272">The maximum allowed length is 64 characters.</span></span>

- <span data-ttu-id="e3952-273">データ フィールドは空にできますが、タブまたはコンマで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-273">A data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="e3952-274">空のデータ フィールドでは、空の文字列値が割り当てらされます。</span><span class="sxs-lookup"><span data-stu-id="e3952-274">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="e3952-275">EndpointName は一意である必要があります。そうしないと、アップロードは失敗します。</span><span class="sxs-lookup"><span data-stu-id="e3952-275">EndpointName must be unique, otherwise the upload fails.</span></span> <span data-ttu-id="e3952-276">同じ EndpointName を使用する重複する行または 2 つの行がある場合、競合により正しくない結合が発生します。</span><span class="sxs-lookup"><span data-stu-id="e3952-276">If there is a duplicate row or two rows that use the same EndpointName the conflict will  cause incorrect joining.</span></span>

- <span data-ttu-id="e3952-277">EndpointLabel1、EndpointLabel2、EndpointLabel3 はカスタマイズ可能なラベルです。</span><span class="sxs-lookup"><span data-stu-id="e3952-277">EndpointLabel1, EndpointLabel2, and EndpointLabel3 are customizable labels.</span></span> <span data-ttu-id="e3952-278">空の文字列または "IT 部門が指定した 2018 Laptop" や "Asset Tag 5678" などの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e3952-278">They can be empty Strings or values such as “IT Department designated 2018 Laptop” or “Asset Tag 5678”.</span></span>

- <span data-ttu-id="e3952-279">行ごとに 7 つの列が必要で、列は次の順序である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-279">There must be seven columns for each row and the columns must be in the following order:</span></span>

  <span data-ttu-id="e3952-280">**フィールドの順序:**</span><span class="sxs-lookup"><span data-stu-id="e3952-280">**Field order:**</span></span>

  <span data-ttu-id="e3952-281">EndpointName、EndpointMake、EndpointModel、EndpointType、EndpointLabel1、EndpointLabel2、EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="e3952-281">EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2,  EndpointLabel3</span></span>

  <span data-ttu-id="e3952-282">**サンプル行:**</span><span class="sxs-lookup"><span data-stu-id="e3952-282">**Sample row:**</span></span>

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a><span data-ttu-id="e3952-283">建物ファイルを更新する</span><span class="sxs-lookup"><span data-stu-id="e3952-283">Update a building file</span></span>

<span data-ttu-id="e3952-284">多くの場合、管理者は建物とサブネットの情報を収集しながら、時間の流れで複数の反復で建物ファイルをアップロードし、利用可能になったら新しいサブネットとその建物情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="e3952-284">While gathering building and subnet information, administrators will often upload the building file in multiple iterations over time, adding new subnets and their building information as it becomes available.</span></span> <span data-ttu-id="e3952-285">この場合は、建物ファイルを再アップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-285">When this occurs, you'll need to re-upload your building file.</span></span> <span data-ttu-id="e3952-286">このプロセスは、前のセクションで説明したように、最初のアップロードと似たもので、次のセクションで説明するいくつかの例外があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-286">This process is like the initial upload as described in the previous section, with a few exceptions as noted in the following section.</span></span>

> [!Important]
> <span data-ttu-id="e3952-287">一度にアクティブにできる建物ファイルは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="e3952-287">Only one building file can be active at a time.</span></span> <span data-ttu-id="e3952-288">複数の建物ファイルは累積的ではありません。</span><span class="sxs-lookup"><span data-stu-id="e3952-288">Multiple building files aren't cumulative.</span></span>

## <a name="add-net-new-subnets"></a><span data-ttu-id="e3952-289">新しいサブネットを追加する</span><span class="sxs-lookup"><span data-stu-id="e3952-289">Add net new subnets</span></span>

<span data-ttu-id="e3952-290">当初はネットワーク トポロジに含めなかった新しい正味サブネットを CQD に追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-290">There are times when you'll need to add net new subnets to CQD that weren't originally part of your network topology.</span></span> <span data-ttu-id="e3952-291">新しいサブネットを追加するには、CQD の [Tenant **Data アップロード** ページから次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e3952-291">To add net new subnets, do the following from the **Tenant Data Upload** page in CQD:</span></span>

1.  <span data-ttu-id="e3952-292">最新のコピーをまだ持ってない場合は、元のファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e3952-292">Download the original file, if you don't already have an up-to-date copy.</span></span>

1.  <span data-ttu-id="e3952-293">CQD で現在のファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="e3952-293">Remove the current file in CQD.</span></span>

1.  <span data-ttu-id="e3952-294">元の建物ファイルを編集し、ネットの新しいサブネットが取得される少なくとも 1 日前に発生する終了日を指定します。</span><span class="sxs-lookup"><span data-stu-id="e3952-294">Edit the original building file and provide an end date that occurs at least one day before the net new subnets were acquired.</span></span>

1.  <span data-ttu-id="e3952-295">net 新しいサブネットを元の建物ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="e3952-295">Append the net new subnets to the original building file.</span></span>

1.  <span data-ttu-id="e3952-296">アップロード変更した建物ファイルを作成し、前の建物ファイルの終了後 1 日の開始日を設定します。</span><span class="sxs-lookup"><span data-stu-id="e3952-296">Upload the newly modified building file, and set the start date for one day after the previous building file ends.</span></span>

## <a name="add-missing-subnets"></a><span data-ttu-id="e3952-297">不足しているサブネットを追加する</span><span class="sxs-lookup"><span data-stu-id="e3952-297">Add missing subnets</span></span>

<span data-ttu-id="e3952-298">管理ネットワークの建物情報をアップロードした後、すべての管理ネットワークに建物の関連付けを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-298">After you upload building information for managed networks, every managed network should have a building association.</span></span> <span data-ttu-id="e3952-299">ただし、必ずしもそうではありません。通常、いくつかのサブネットが欠落しています。</span><span class="sxs-lookup"><span data-stu-id="e3952-299">However, this won't always be the case; typically, a few subnets are missed.</span></span> <span data-ttu-id="e3952-300">これらの不足しているネットワークを見つけるには、CQD の [Quality **of Experience Reports]** ページで[不足しているサブネット レポート] を確認します。 </span><span class="sxs-lookup"><span data-stu-id="e3952-300">To find these missing networks, review the **Missing Subnet Report** on the **Quality of Experience Reports** page in CQD.</span></span> <span data-ttu-id="e3952-301">これにより、建物のデータ ファイルで定義されていない、外部としてマークされている 10 以上のオーディオ ストリームを持つすべてのサブネットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3952-301">This presents all the subnets with 10 or more audio streams that aren't defined in the building data file and are being marked as outside.</span></span> <span data-ttu-id="e3952-302">この一覧にマネージド ネットワークが含まれるのが 1 つも表示されません。</span><span class="sxs-lookup"><span data-stu-id="e3952-302">Ensure that there are no managed networks in this list.</span></span> <span data-ttu-id="e3952-303">サブネットが見つからない場合は、次の手順に従って、元の建物データ ファイルを更新し、CQD に再アップロードします。</span><span class="sxs-lookup"><span data-stu-id="e3952-303">If subnets are missing, use the following procedure to update the original building data file and re-upload it to CQD.</span></span>

1. <span data-ttu-id="e3952-304">CQD **の [Tenant Data アップロード]** ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e3952-304">Go to the **Tenant Data Upload** page in CQD.</span></span>

1. <span data-ttu-id="e3952-305">最新のコピーをまだ持ってない場合は、元のファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e3952-305">Download the original file, if you don't already have an up-to-date copy.</span></span>

1. <span data-ttu-id="e3952-306">CQD で現在のファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="e3952-306">Remove the current file in CQD.</span></span>

1. <span data-ttu-id="e3952-307">新しいサブネットを元のファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="e3952-307">Append the new subnets to the original file.</span></span>

1. <span data-ttu-id="e3952-308">アップロードファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e3952-308">Upload the building file.</span></span> <span data-ttu-id="e3952-309">CQD が履歴データを処理するには、開始日を少なくとも 8 か月前に設定してください。</span><span class="sxs-lookup"><span data-stu-id="e3952-309">Be sure to set the start date to at least eight months prior so that CQD will process historical data.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="e3952-310">レポートをフィルター処理して組織のテナント データのみを表示するには、このレポートに 2 番目のテナント ID のクエリ フィルターとしてテナント **ID** を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3952-310">You'll need to add your tenant ID as a query filter for **Second Tenant ID** to this report to filter the report to view only your organization's tenant data.</span></span> <span data-ttu-id="e3952-311">それ以外の場合、レポートにはフェデレーション サブネットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3952-311">Otherwise, the report will show federated subnets.</span></span>

> [!NOTE] 
> <span data-ttu-id="e3952-312">Month Year レポート フィルターは、必ず当月に合わせて調整してください。</span><span class="sxs-lookup"><span data-stu-id="e3952-312">Be sure to adjust the Month Year report filter to the current month.</span></span> <span data-ttu-id="e3952-313">[ **編集] を** 選択し、[月の年 **] レポート** フィルターを調整して、新しい既定の月を保存します。</span><span class="sxs-lookup"><span data-stu-id="e3952-313">Select **Edit**, and adjust the **Month Year** report filter to save the new default month.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e3952-314">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e3952-314">Related topics</span></span>

[<span data-ttu-id="e3952-315">CQD の建物マップを作成する</span><span class="sxs-lookup"><span data-stu-id="e3952-315">Create a building map for CQD</span></span>](CQD-building-mapping.md)

[<span data-ttu-id="e3952-316">Teams の通話品質の向上と監視</span><span class="sxs-lookup"><span data-stu-id="e3952-316">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="e3952-317">CQD とは</span><span class="sxs-lookup"><span data-stu-id="e3952-317">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="e3952-318">通話品質ダッシュボード (CQD) を設定する</span><span class="sxs-lookup"><span data-stu-id="e3952-318">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="e3952-319">CQD データとレポート</span><span class="sxs-lookup"><span data-stu-id="e3952-319">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="e3952-320">CQD を使用して通話と会議の品質を管理する</span><span class="sxs-lookup"><span data-stu-id="e3952-320">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="e3952-321">CQD で使用可能なディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="e3952-321">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="e3952-322">CQD のストリーム分類</span><span class="sxs-lookup"><span data-stu-id="e3952-322">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="e3952-323">CQD Power BI分析するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e3952-323">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
