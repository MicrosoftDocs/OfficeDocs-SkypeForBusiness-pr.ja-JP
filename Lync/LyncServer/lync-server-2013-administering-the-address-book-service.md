---
title: 'Lync Server 2013: アドレス帳サービスの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ea7a68d77acd7bbaf3de43fce38c0e85c02dad4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="99d0a-102">Lync Server 2013 でのアドレス帳サービスの管理</span><span class="sxs-lookup"><span data-stu-id="99d0a-102">Administering the Address Book Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99d0a-103">_**トピックの最終更新日:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="99d0a-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="99d0a-104">Lync Server Enterprise Edition または Standard Edition サーバーの展開の一環として、アドレス帳サービスは既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-104">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="99d0a-105">アドレス帳サービスによって使用されるデータベース (RTCab) は、SQL Server 上に作成されます (Enterprise Edition の場合は、バックエンドの SQL Server、SQL Server の場合は、SQL Server の場合は、SQL Server が併置されています)。</span><span class="sxs-lookup"><span data-stu-id="99d0a-105">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="99d0a-106"><STRONG>Adsi edit</STRONG>を使用して Active Directory ドメインサービスオブジェクトの属性を編集する方法については、「 <A href="http://go.microsoft.com/fwlink/?linkid=330427">adsi edit</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99d0a-106">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="99d0a-107">特にアドレス帳サービス用のリソースキットのツールの詳細については、「 <A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 リソースキットツール</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99d0a-107">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="99d0a-108">アドレス帳サーバーの電話番号正規化</span><span class="sxs-lookup"><span data-stu-id="99d0a-108">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="99d0a-109">Lync Server には、標準化された RFC 3966/e.164 電話番号が必要です。</span><span class="sxs-lookup"><span data-stu-id="99d0a-109">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="99d0a-110">構造化されていない、または一貫性のない形式の電話番号を使用する場合、Lync Server はアドレス帳サーバーに依存して、正規化ルールに渡される前に電話番号の事前処理を行います。</span><span class="sxs-lookup"><span data-stu-id="99d0a-110">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="99d0a-111">アドレス帳から電話番号を使用し、正規化ルールを適用すると、Lync Phone Edition や Lync Mobile などのクライアントは、これらの正規化された数値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-111">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="99d0a-p104">以前のバージョンで使用されていた正規化ルールは、いくつかの調整を行わなければ適切に動作しない場合があります。空白文字や不要な文字は正規化ルールの前に削除されるため、特にダッシュや削除された文字を正規表現で検索している場合、正規化ルールがエラーになることがあります。こういった不要な文字を検索していないことと、ルールの想定の場所に文字が存在しない場合にルールが問題なくエラーになって続行するよう、正規化ルールを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99d0a-p104">The normalization rules that were used in previous versions may not work properly without some adjustments. Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail. You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="99d0a-115">ユーザー レプリケーターとアドレス帳サーバー</span><span class="sxs-lookup"><span data-stu-id="99d0a-115">User Replicator and Address Book Server</span></span>

<span data-ttu-id="99d0a-116">アドレス帳サーバーは、ユーザー レプリケーターが提供するデータを使用して、グローバル アドレス一覧 (GAL) から最初に取得する情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="99d0a-116">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="99d0a-117">ユーザーレプリケーターは、各ユーザー、連絡先、およびグループの Active Directory ドメインサービスの属性をデータベースの AbUserEntry テーブルに書き込み、アドレス帳サーバーは、データベースのユーザーデータをアドレス帳サーバーのファイルストア内のファイルに同期し、アドレス帳データベース RTCab に入ります。</span><span class="sxs-lookup"><span data-stu-id="99d0a-117">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="99d0a-118">AbUserEntry テーブルのスキーマは、**UserGuid** および **UserData** の 2 つの列を使用します。</span><span class="sxs-lookup"><span data-stu-id="99d0a-118">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="99d0a-119">**Userguid**はインデックス列で、Active Directory オブジェクトの16バイトの GUID を含みます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-119">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="99d0a-120">**UserData**は、その連絡先に対して前述した Active Directory ドメインサービスのすべての属性を含む image 列です。</span><span class="sxs-lookup"><span data-stu-id="99d0a-120">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="99d0a-121">ユーザーレプリケーターは、AbUserEntry テーブルと同じ SQL Server ベースのインスタンスにある構成テーブルを読み取ることによって、どの Active Directory 属性を書き込むかを決定します。</span><span class="sxs-lookup"><span data-stu-id="99d0a-121">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="99d0a-122">AbAttribute テーブルには、**ID**、**名前**、**フラグ**、**有効** の 4 つの列があります。</span><span class="sxs-lookup"><span data-stu-id="99d0a-122">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="99d0a-123">このテーブルはデータベースのセットアップ中に作成されます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-123">The table is created during database setup.</span></span> <span data-ttu-id="99d0a-124">AbAttribute テーブルが空の場合、ユーザー レプリケーターはその AbUserEntry テーブル処理ロジックをスキップします。</span><span class="sxs-lookup"><span data-stu-id="99d0a-124">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="99d0a-125">アドレス帳サーバーの属性は動的で、AbAttribute テーブルから取得され、アドレス帳サーバーがアクティブ化される際、アドレス帳サーバーによって最初に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-125">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="99d0a-126">アドレス帳サーバーのアクティブ化は、AbAttribute テーブルに、次の表に示す値を設定します。</span><span class="sxs-lookup"><span data-stu-id="99d0a-126">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99d0a-127">ID</span><span class="sxs-lookup"><span data-stu-id="99d0a-127">ID</span></span></th>
<th><span data-ttu-id="99d0a-128">名前</span><span class="sxs-lookup"><span data-stu-id="99d0a-128">Name</span></span></th>
<th><span data-ttu-id="99d0a-129">フラグ</span><span class="sxs-lookup"><span data-stu-id="99d0a-129">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-130">1 </span><span class="sxs-lookup"><span data-stu-id="99d0a-130">1</span></span></p></td>
<td><p><span data-ttu-id="99d0a-131">givenName</span><span class="sxs-lookup"><span data-stu-id="99d0a-131">givenName</span></span></p></td>
<td><p><span data-ttu-id="99d0a-132">0x01400000</span><span class="sxs-lookup"><span data-stu-id="99d0a-132">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d0a-133">2 </span><span class="sxs-lookup"><span data-stu-id="99d0a-133">2</span></span></p></td>
<td><p><span data-ttu-id="99d0a-134">Sn</span><span class="sxs-lookup"><span data-stu-id="99d0a-134">Sn</span></span></p></td>
<td><p><span data-ttu-id="99d0a-135">0x02400000</span><span class="sxs-lookup"><span data-stu-id="99d0a-135">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-136">3 </span><span class="sxs-lookup"><span data-stu-id="99d0a-136">3</span></span></p></td>
<td><p><span data-ttu-id="99d0a-137">displayName</span><span class="sxs-lookup"><span data-stu-id="99d0a-137">displayName</span></span></p></td>
<td><p><span data-ttu-id="99d0a-138">0x03420000</span><span class="sxs-lookup"><span data-stu-id="99d0a-138">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d0a-139">4 </span><span class="sxs-lookup"><span data-stu-id="99d0a-139">4</span></span></p></td>
<td><p><span data-ttu-id="99d0a-140">タイトル</span><span class="sxs-lookup"><span data-stu-id="99d0a-140">Title</span></span></p></td>
<td><p><span data-ttu-id="99d0a-141">0x04000000</span><span class="sxs-lookup"><span data-stu-id="99d0a-141">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-142">5 </span><span class="sxs-lookup"><span data-stu-id="99d0a-142">5</span></span></p></td>
<td><p><span data-ttu-id="99d0a-143">mailNickname</span><span class="sxs-lookup"><span data-stu-id="99d0a-143">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="99d0a-144">0x05400000</span><span class="sxs-lookup"><span data-stu-id="99d0a-144">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d0a-145">6 </span><span class="sxs-lookup"><span data-stu-id="99d0a-145">6</span></span></p></td>
<td><p><span data-ttu-id="99d0a-146">Company</span><span class="sxs-lookup"><span data-stu-id="99d0a-146">Company</span></span></p></td>
<td><p><span data-ttu-id="99d0a-147">0x06000000</span><span class="sxs-lookup"><span data-stu-id="99d0a-147">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-148">7 </span><span class="sxs-lookup"><span data-stu-id="99d0a-148">7</span></span></p></td>
<td><p><span data-ttu-id="99d0a-149">physicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="99d0a-149">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="99d0a-150">0x07000000</span><span class="sxs-lookup"><span data-stu-id="99d0a-150">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d0a-151">8 </span><span class="sxs-lookup"><span data-stu-id="99d0a-151">8</span></span></p></td>
<td><p><span data-ttu-id="99d0a-152">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="99d0a-152">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="99d0a-153">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="99d0a-153">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-154">9 </span><span class="sxs-lookup"><span data-stu-id="99d0a-154">9</span></span></p></td>
<td><p><span data-ttu-id="99d0a-155">telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="99d0a-155">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="99d0a-156">0x09022800</span><span class="sxs-lookup"><span data-stu-id="99d0a-156">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d0a-157">10 </span><span class="sxs-lookup"><span data-stu-id="99d0a-157">10</span></span></p></td>
<td><p><span data-ttu-id="99d0a-158">homePhone</span><span class="sxs-lookup"><span data-stu-id="99d0a-158">homePhone</span></span></p></td>
<td><p><span data-ttu-id="99d0a-159">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="99d0a-159">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-160">#</span><span class="sxs-lookup"><span data-stu-id="99d0a-160">11</span></span></p></td>
<td><p><span data-ttu-id="99d0a-161">Mobile</span><span class="sxs-lookup"><span data-stu-id="99d0a-161">Mobile</span></span></p></td>
<td><p><span data-ttu-id="99d0a-162">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="99d0a-162">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d0a-163">12</span><span class="sxs-lookup"><span data-stu-id="99d0a-163">12</span></span></p></td>
<td><p><span data-ttu-id="99d0a-164">otherTelephone</span><span class="sxs-lookup"><span data-stu-id="99d0a-164">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="99d0a-165">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="99d0a-165">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-166">スリー</span><span class="sxs-lookup"><span data-stu-id="99d0a-166">13</span></span></p></td>
<td><p><span data-ttu-id="99d0a-167">ipPhone</span><span class="sxs-lookup"><span data-stu-id="99d0a-167">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="99d0a-168">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="99d0a-168">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d0a-169">14 </span><span class="sxs-lookup"><span data-stu-id="99d0a-169">14</span></span></p></td>
<td><p><span data-ttu-id="99d0a-170">メール</span><span class="sxs-lookup"><span data-stu-id="99d0a-170">Mail</span></span></p></td>
<td><p><span data-ttu-id="99d0a-171">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="99d0a-171">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-172">15 </span><span class="sxs-lookup"><span data-stu-id="99d0a-172">15</span></span></p></td>
<td><p><span data-ttu-id="99d0a-173">groupType</span><span class="sxs-lookup"><span data-stu-id="99d0a-173">groupType</span></span></p></td>
<td><p><span data-ttu-id="99d0a-174">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="99d0a-174">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d0a-175">16 </span><span class="sxs-lookup"><span data-stu-id="99d0a-175">16</span></span></p></td>
<td><p><span data-ttu-id="99d0a-176">部署</span><span class="sxs-lookup"><span data-stu-id="99d0a-176">Department</span></span></p></td>
<td><p><span data-ttu-id="99d0a-177">0x10000000</span><span class="sxs-lookup"><span data-stu-id="99d0a-177">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-178">17 </span><span class="sxs-lookup"><span data-stu-id="99d0a-178">17</span></span></p></td>
<td><p><span data-ttu-id="99d0a-179">説明</span><span class="sxs-lookup"><span data-stu-id="99d0a-179">Description</span></span></p></td>
<td><p><span data-ttu-id="99d0a-180">0x11000100</span><span class="sxs-lookup"><span data-stu-id="99d0a-180">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d0a-181">18 </span><span class="sxs-lookup"><span data-stu-id="99d0a-181">18</span></span></p></td>
<td><p><span data-ttu-id="99d0a-182">Manager</span><span class="sxs-lookup"><span data-stu-id="99d0a-182">Manager</span></span></p></td>
<td><p><span data-ttu-id="99d0a-183">0x12040001</span><span class="sxs-lookup"><span data-stu-id="99d0a-183">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-184">年</span><span class="sxs-lookup"><span data-stu-id="99d0a-184">19</span></span></p></td>
<td><p><span data-ttu-id="99d0a-185">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="99d0a-185">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="99d0a-186">0x00500105</span><span class="sxs-lookup"><span data-stu-id="99d0a-186">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d0a-187">1280</span><span class="sxs-lookup"><span data-stu-id="99d0a-187">20</span></span></p></td>
<td><p><span data-ttu-id="99d0a-188">msExchHideFromAddressLists</span><span class="sxs-lookup"><span data-stu-id="99d0a-188">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="99d0a-189">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="99d0a-189">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-190">99</span><span class="sxs-lookup"><span data-stu-id="99d0a-190">99</span></span></p></td>
<td><p><span data-ttu-id="99d0a-191">entryID</span><span class="sxs-lookup"><span data-stu-id="99d0a-191">entryID</span></span></p></td>
<td><p><span data-ttu-id="99d0a-192">0x99000000</span><span class="sxs-lookup"><span data-stu-id="99d0a-192">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="99d0a-193">**ID** 列の数字は一意である必要があり、再利用は一切できません。</span><span class="sxs-lookup"><span data-stu-id="99d0a-193">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="99d0a-194">また、ID の値を 256 未満に保つことで、アドレス帳サーバーにより書き込まれる出力ファイルの領域を確保します。</span><span class="sxs-lookup"><span data-stu-id="99d0a-194">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="99d0a-195">しかし、最大 ID 値は 65535 です。</span><span class="sxs-lookup"><span data-stu-id="99d0a-195">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="99d0a-196">**Name**列は、ユーザーレプリケーターが連絡先ごとに AbUserEntry テーブルに格納する Active Directory 属性の名前に対応しています。</span><span class="sxs-lookup"><span data-stu-id="99d0a-196">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="99d0a-197">**フラグ**列の値は、属性の種類の定義に使用されます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-197">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="99d0a-198">次の種類のアドレス帳サーバー属性はユーザー レプリケーターにより認識され、**フラグ**列の値の低バイト数で示されます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-198">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99d0a-199">属性</span><span class="sxs-lookup"><span data-stu-id="99d0a-199">Attribute</span></span></th>
<th><span data-ttu-id="99d0a-200">説明</span><span class="sxs-lookup"><span data-stu-id="99d0a-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-201">0x0</span><span class="sxs-lookup"><span data-stu-id="99d0a-201">0x0</span></span></p></td>
<td><p><span data-ttu-id="99d0a-p108">文字列属性です。 ユーザー レプリケーターは、AbUserEntry テーブルに格納する前に、この型を UTF-8 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="99d0a-p108">A string attribute. User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d0a-204">0x1</span><span class="sxs-lookup"><span data-stu-id="99d0a-204">0x1</span></span></p></td>
<td><p><span data-ttu-id="99d0a-p109">バイナリ属性です。 ユーザー レプリケーターは、これを変換することなく BLOB に格納します</span><span class="sxs-lookup"><span data-stu-id="99d0a-p109">A binary attribute. User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-207">0x2</span><span class="sxs-lookup"><span data-stu-id="99d0a-207">0x2</span></span></p></td>
<td><p><span data-ttu-id="99d0a-208">文字列属性ですが、属性値が&quot;tel:&quot;から始まる場合にのみ含まれます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-208">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="99d0a-209">これは、主に複数値の文字列属性 (具体的には<strong>proxyAddresses</strong>です。</span><span class="sxs-lookup"><span data-stu-id="99d0a-209">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="99d0a-210">この場合、アドレス帳サーバーは、tel: &quot;&quot;から始まる<strong>proxyAddresses</strong>エントリのみに注目します。</span><span class="sxs-lookup"><span data-stu-id="99d0a-210">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="99d0a-211">そのため、領域を節約するために、ユーザーレプリケーターには、tel: &quot;&quot;から始まるエントリのみが格納されます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-211">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d0a-212">0x3</span><span class="sxs-lookup"><span data-stu-id="99d0a-212">0x3</span></span></p></td>
<td><p><span data-ttu-id="99d0a-p111">ブール値の文字列属性です。TRUE の場合、ユーザー レプリケーターはこの連絡先を AbUserEntry テーブルに含めません。 FALSE の場合、ユーザー レプリケーターはこの連絡先の属性を AbUserEntry テーブルに含めますが、このフラグを持つ特定の属性は含めません。 これは、主に <strong>msExchHideFromAddressLists</strong> 属性用である、もう 1 つの特例の型です。</span><span class="sxs-lookup"><span data-stu-id="99d0a-p111">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table. If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag. This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-216">0x4</span><span class="sxs-lookup"><span data-stu-id="99d0a-216">0x4</span></span></p></td>
<td><p><span data-ttu-id="99d0a-217">文字列&quot;属性。ただし、属性値が smtp&quot;で始まる場合にのみ含まれます。この&quot; @ &quot;記号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="99d0a-217">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d0a-218">0x5</span><span class="sxs-lookup"><span data-stu-id="99d0a-218">0x5</span></span></p></td>
<td><p><span data-ttu-id="99d0a-219">文字列属性。ただし、 &quot;属性値が tel:&quot;または&quot;smtp:&quot;で始まる場合にのみ含まれ、 &quot; @ &quot;記号を含みます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-219">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-220">0x100</span><span class="sxs-lookup"><span data-stu-id="99d0a-220">0x100</span></span></p></td>
<td><p><span data-ttu-id="99d0a-221">設定されている場合、これは各連絡先で複数回出現可能な複数値の属性です。</span><span class="sxs-lookup"><span data-stu-id="99d0a-221">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d0a-222">解像度</span><span class="sxs-lookup"><span data-stu-id="99d0a-222">0x400</span></span></p></td>
<td><p><span data-ttu-id="99d0a-p112">設定されている場合、これは連絡先の電子メール ユーザー アカウント名の属性を示します。 アドレス帳サーバーはこのフラグを使用して、電話正規化イベント ログのエントリに表示する属性値を特定します。</span><span class="sxs-lookup"><span data-stu-id="99d0a-p112">If set, this identifies the email user account name attribute for a contact. Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-225">0x800</span><span class="sxs-lookup"><span data-stu-id="99d0a-225">0x800</span></span></p></td>
<td><p><span data-ttu-id="99d0a-p113">設定されている場合、これは連絡先の必須属性を示します。 アドレス帳サーバーは、Active Directory にこの属性の値がある場合のみ、ユーザーを AbUserEntry テーブルに含めます。 必須属性が複数ある場合、ユーザーを AbUserEntry テーブルに含めるには、その中の 1 つのみに値があることが必要です。</span><span class="sxs-lookup"><span data-stu-id="99d0a-p113">If set, this identifies a required attribute for a contact. Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory. If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d0a-229">0x1000</span><span class="sxs-lookup"><span data-stu-id="99d0a-229">0x1000</span></span></p></td>
<td><p><span data-ttu-id="99d0a-230">設定されている場合、アドレス帳サーバーはこの属性の値を常に正規化します。</span><span class="sxs-lookup"><span data-stu-id="99d0a-230">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-231">0x2000</span><span class="sxs-lookup"><span data-stu-id="99d0a-231">0x2000</span></span></p></td>
<td><p><span data-ttu-id="99d0a-232">設定されている場合、アドレス帳サーバーは <strong>UseNormalizationRules</strong> CMS 設定が FALSE の場合は <strong>proxyAddresses</strong> からの正規化された番号を使用し、それ以外の場合はフラグ ビットが 0x1000 のときと同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="99d0a-232">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d0a-233">0x4000</span><span class="sxs-lookup"><span data-stu-id="99d0a-233">0x4000</span></span></p></td>
<td><p><span data-ttu-id="99d0a-p114">設定されている場合、アドレス帳サーバーは、指定された属性にこの値を持つオブジェクトを AbUserEntry テーブルに含めません。 たとえば、<strong>msRTCSIP-PrimaryUserAddress</strong> 属性がこのフラグ ビット セットを持つ場合、この属性を持つ連絡先はデータベースに書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="99d0a-p114">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute. For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-236">0x8000</span><span class="sxs-lookup"><span data-stu-id="99d0a-236">0x8000</span></span></p></td>
<td><p><span data-ttu-id="99d0a-p115">設定されている場合、アドレス帳サーバーは、指定された属性にこの値を持たないオブジェクトを AbUserEntry テーブルに含めません。 0x4000 と 0x8000 の両方のフラグ ビットがオブジェクトに対して設定されている場合は、0x4000 に設定されたフラグ ビット値を持つ属性が優先され、オブジェクトは AbUserEntry テーブルから除外されます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-p115">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute. If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d0a-239">「その他」</span><span class="sxs-lookup"><span data-stu-id="99d0a-239">0x10000</span></span></p></td>
<td><p><span data-ttu-id="99d0a-p116">設定されている場合、これはグループ オブジェクトを表します。 ユーザー レプリケーターはこのフラグ ビットを使用して、その存在がグループを示す<strong>groupType</strong> 属性を持つ連絡先を含めます (例: 配布リストまたはセキュリティ グループ)。</span><span class="sxs-lookup"><span data-stu-id="99d0a-p116">If set, this represents a group object. User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-242">0x20000</span><span class="sxs-lookup"><span data-stu-id="99d0a-242">0x20000</span></span></p></td>
<td><p><span data-ttu-id="99d0a-243">設定されている場合、ユーザー レプリケーターはこのフラグ ビットを使用して、デバイス固有のアドレス帳サーバー ファイル (つまり、.dabs の拡張子を持つファイル) にこの属性を含めます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-243">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="99d0a-244">以前のバージョンの Lync Server では、Active Directory への変更を適用する際に、管理者は、 **Update-csaddressbook** Windows PowerShell コマンドレット**を実行して、** lync Server ユーザーデータベースおよび rtcab データベースへの変更を直ちに保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99d0a-244">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="99d0a-245">Lync Server 2013 の Lync Server ユーザーレプリケーターは、Active Directory から変更を取得し、構成された間隔に基づいて Lync Server ユーザーデータベースを更新します。</span><span class="sxs-lookup"><span data-stu-id="99d0a-245">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="99d0a-246">Lync Server ユーザーレプリケーターでは、管理者が Update-csaddressbook を実行しなくても、変更内容が RTCab データベースに迅速に伝達されます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-246">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="99d0a-247">アドレス帳 Web クエリが有効になっている場合、変更は Lync クライアントによって検索結果に反映されます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-247">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="99d0a-248">アドレス帳ファイルのダウンロードが有効になっている場合にのみ、管理者は Update-csaddressbook を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99d0a-248">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="99d0a-249">既定では、Lync Server ユーザーレプリケーターは5分ごとに自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-249">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="99d0a-250">この間隔は、ReplicationCycleInterval &lt; &gt;を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-250">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="99d0a-251">アドレス帳のフィルター処理</span><span class="sxs-lookup"><span data-stu-id="99d0a-251">Filtering the Address Book</span></span>

<span data-ttu-id="99d0a-252">アドレス帳サーバーファイルで設定されたユーザーは、AbAttribute テーブルにリストされている特定の Active Directory ドメインサービス属性に基づいて制御できます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-252">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="99d0a-253">そのようなフィルター処理に使用される属性の 1 つは、**msExchangeHideFromAddressBook** 属性です。</span><span class="sxs-lookup"><span data-stu-id="99d0a-253">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="99d0a-254">これは、Exchange スキーマによって追加されるユーザー属性です。</span><span class="sxs-lookup"><span data-stu-id="99d0a-254">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="99d0a-255">この属性の値が TRUE に設定されている場合、Exchange Server はこの属性を使用し、Outlook のグローバル アドレス一覧 (GAL) で連絡先を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="99d0a-255">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="99d0a-256">同様に、この属性の値が TRUE の場合、ユーザー レプリケーターはそのユーザーを AbUserEntry テーブルに含めず、このユーザーはアドレス帳サーバー ファイルに存在しなくなります。</span><span class="sxs-lookup"><span data-stu-id="99d0a-256">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="99d0a-p120">一部のフラグ ビットを使用して、アドレス帳サーバー属性に対して使用するフィルターを定義できます。 たとえば、特定のフラグ ビットがあることにより、ある属性を include 属性か exclude 属性として指定できます。 ユーザー レプリケーターは、exclude 属性を含む連絡先を除外したり、include 属性を含まない連絡先を除外したりします。</span><span class="sxs-lookup"><span data-stu-id="99d0a-p120">You can use some flag bits to define a filter to use on Address Book Server attributes. For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute. User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="99d0a-260">アドレス帳のフィルター処理の詳細については、「 <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Lync server 2013 のアドレス帳サーバーのコマンドレット</A>」および「 <A href="http://go.microsoft.com/fwlink/?linkid=330430">lync 2013 アドレス帳のフィルター処理</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99d0a-260">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="http://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="99d0a-p121">現在は 3 種類のフィルターがあります。 次の表にこれら 3 つのフィルターの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="99d0a-p121">Currently, there are three different filters. The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99d0a-263">属性</span><span class="sxs-lookup"><span data-stu-id="99d0a-263">Attribute</span></span></th>
<th><span data-ttu-id="99d0a-264">説明</span><span class="sxs-lookup"><span data-stu-id="99d0a-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-265">0x800</span><span class="sxs-lookup"><span data-stu-id="99d0a-265">0x800</span></span></p></td>
<td><p><span data-ttu-id="99d0a-p122">設定されている場合、これは連絡先の必須属性を示します。 ユーザー レプリケーターはこのフラグ ビットを使用し、必須属性を少なくとも 1 つ含んでいない連絡先を除外します。 OuPathId は必須属性で、必ず設定されます。 そのため、その他の必須属性が少なくとも 1 つ設定される必要があります。 それ以外の場合、(つまり、必須属性 OuPathId の値を持つ) 連絡先は、データベースにまだ書き込まれません。 たとえば、<strong>telephoneNumber</strong> と <strong>homePhone</strong> が必須の属性として定義されている場合、これらの属性のうち少なくとも 1 つを持つ連絡先のみがデータベースに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-p122">If set, this identifies a required attribute for a contact. User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute. The OuPathId is a required attribute, which is always set. So at least one of other required attributes should be set. Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database. For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d0a-272">0x4000</span><span class="sxs-lookup"><span data-stu-id="99d0a-272">0x4000</span></span></p></td>
<td><p><span data-ttu-id="99d0a-p123">設定されている場合、exclude 属性を示します。 ユーザー レプリケーターはこのフラグ ビットを使用し、この属性を含む連絡先を除外します。 たとえば、<strong>msRTCSIP-PrimaryUserAddress</strong> が exclude 属性として定義されている場合、この属性を持つ連絡先はデータベースに書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="99d0a-p123">If set, this identifies an exclude attribute. User Replicator uses this flag bit to filter out contacts that contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d0a-276">0x8000</span><span class="sxs-lookup"><span data-stu-id="99d0a-276">0x8000</span></span></p></td>
<td><p><span data-ttu-id="99d0a-p124">設定されている場合、これは include 属性を示します。 ユーザー レプリケーターはこのフラグ ビットを使用し、この属性を含まない連絡先を除外します。 たとえば、<strong>msRTCSIP-PrimaryUserAddress</strong> が include 属性として定義されている場合、この属性を持つ連絡先のみがデータベースに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-p124">If set, this identifies an include attribute. User Replicator uses this flag bit to filter out contacts that do not contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="99d0a-280">0x4000 (exclude 属性) と 0x8000 (include 属性) の両方のフラグ ビットが設定されている場合、0x4000 ビットが 0x8000 ビットより優先され、連絡先は除外されます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-280">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="99d0a-p125">アドレス帳をフィルターして特定のユーザーのみを含めることができますが、エントリを制限すると、他のユーザーがフィルターされたユーザーへ連絡したり、プレゼンス状態を参照したりできる範囲が制限されます。ユーザーは、ユーザーの完全なサインイン名を入力することで、アドレス帳にないユーザーに対する検索、インスタント メッセージの手動送信、手動での通話の開始をいつでも実行できます。また、ユーザーの連絡先情報は、Outlook でも検索できます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-p125">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status. Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name. Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="99d0a-284">アドレス帳ファイルに完全な連絡先レコードがある場合でも、Lync Server を使用して、セッションの開始を行うように構成されていないユーザーとの電子メール、電話、またはエンタープライズの音声通話 (サーバーでエンタープライズ Voip が有効になっている場合) を開始することができます。Protocol (SIP)、一部の組織では、アドレス帳サーバーのエントリに SIP が有効なユーザーのみを含めることを希望しています。</span><span class="sxs-lookup"><span data-stu-id="99d0a-284">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="99d0a-285">次の必須属性 ( **mailNickname**、 **telephoneNumber**、 **homePhone**、および**mobile**) の**Flags**列で0X800 ビットをクリアすることによって、アドレス帳にフィルターを適用して、SIP が有効なユーザーのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-285">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="99d0a-286">**MsRTCSIP-PrimaryUserAddress**属性の**Flags**列に 0x8000 (include 属性) を設定して、SIP が有効なユーザーのみを含めるようにアドレス帳にフィルターを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-286">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="99d0a-287">これにより、アドレス帳ファイルからサービスアカウントを除外することもできます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-287">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="99d0a-288">AbAttribute テーブルを変更した後、コマンドレット **Update-CsUserDatabase** のコマンドを実行し、AbUserEntry テーブルのデータを更新できます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-288">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="99d0a-289">UR のレプリケーションが完了した後、コマンドレット **UpdateCsAddressBook** のコマンドを手動で実行し、アドレス帳サーバー ファイル ストアのファイルを更新できます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-289">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="99d0a-290">アドレス帳サーバーが配置されているフロントエンドサーバーは、管理上構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="99d0a-290">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="99d0a-291">展開時に1つが選択されます (通常は最初のフロントエンドサーバーが展開されます)。</span><span class="sxs-lookup"><span data-stu-id="99d0a-291">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="99d0a-292">障害が発生した場合、アドレス帳サービスは別のフロントエンドサーバーに移動し、管理上の注意を必要としません。</span><span class="sxs-lookup"><span data-stu-id="99d0a-292">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="99d0a-293">複数フォレスト展開または親子展開 (インフラストラクチャの統合など) からインフラストラクチャを統合または変更している場合は、一部のユーザーについてアドレス帳サービスのダウンロードとアドレス帳 Web クエリが失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="99d0a-293">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="99d0a-294">複数のドメインやフォレストがある展開内では、問題の発生しているユーザー オブジェクトに属性 <STRONG>MsRTCSIP-OriginatorSid</STRONG> が追加されます。</span><span class="sxs-lookup"><span data-stu-id="99d0a-294">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="99d0a-295">問題を解決するには、これらのオブジェクトの <STRONG>MsRTCSIP-OriginatorSid</STRONG> 属性を NULL に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99d0a-295">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

