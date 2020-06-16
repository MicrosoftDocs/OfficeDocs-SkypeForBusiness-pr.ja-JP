---
title: アドレス帳を移行する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee0dc4d50fb3b60d4f6a9581d497df11da630122
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="81a7d-102">アドレス帳を移行する</span><span class="sxs-lookup"><span data-stu-id="81a7d-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81a7d-103">_**トピックの最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="81a7d-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="81a7d-104">一般に、Lync Server 2010 アドレス帳は、他のトポロジと一緒に移行されます。</span><span class="sxs-lookup"><span data-stu-id="81a7d-104">In general, the Lync Server 2010 Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="81a7d-105">ただし、Lync Server 2010 環境で次のようにカスタマイズした場合は、移行後の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81a7d-105">However, you might need to perform some post-migration steps if you customized the following in your Lync Server 2010 environment:</span></span>

  - <span data-ttu-id="81a7d-106">アドレス帳のエントリを組織単位 (OU) ごとにグループ化する **PartitionbyOU** WMI プロパティを設定した場合。</span><span class="sxs-lookup"><span data-stu-id="81a7d-106">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span>

  - <span data-ttu-id="81a7d-107">アドレス帳の正規化ルールをカスタマイズした場合。</span><span class="sxs-lookup"><span data-stu-id="81a7d-107">Customized the Address Book normalization rules.</span></span>

  - <span data-ttu-id="81a7d-108">**UseNormalizationRules** の既定の値を False に変更した場合。</span><span class="sxs-lookup"><span data-stu-id="81a7d-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span>

<span data-ttu-id="81a7d-109">**グループ化されたアドレス帳のエントリ**</span><span class="sxs-lookup"><span data-stu-id="81a7d-109">**Grouped Address Book Entries**</span></span>

<span data-ttu-id="81a7d-110">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries.</span><span class="sxs-lookup"><span data-stu-id="81a7d-110">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries.</span></span> <span data-ttu-id="81a7d-111">You might want to group address book entries to limit the scope of Address Book searches.</span><span class="sxs-lookup"><span data-stu-id="81a7d-111">You might want to group address book entries to limit the scope of Address Book searches.</span></span> <span data-ttu-id="81a7d-112">To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together.</span><span class="sxs-lookup"><span data-stu-id="81a7d-112">To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together.</span></span> <span data-ttu-id="81a7d-113">For example, assign a single value for all the users in an OU.</span><span class="sxs-lookup"><span data-stu-id="81a7d-113">For example, assign a single value for all the users in an OU.</span></span>

<span data-ttu-id="81a7d-114">**アドレス帳の正規化ルール**</span><span class="sxs-lookup"><span data-stu-id="81a7d-114">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="81a7d-115">Lync Server 2010 環境でアドレス帳の正規化ルールをカスタマイズした場合は、カスタマイズしたルールをパイロットプールに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81a7d-115">If you customized Address Book normalization rules in your Lync Server 2010 environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="81a7d-116">アドレス帳の正規化ルールをカスタマイズしていない場合は、アドレス帳サービスで移行するものは何もありません。</span><span class="sxs-lookup"><span data-stu-id="81a7d-116">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="81a7d-117">Lync server 2013 の既定の正規化ルールは、Lync Server 2010 の既定のルールと同じです。</span><span class="sxs-lookup"><span data-stu-id="81a7d-117">The default normalization rules for Lync Server 2013 are the same as the default rules for Lync Server 2010.</span></span> <span data-ttu-id="81a7d-118">カスタマイズした正規化ルールを移行するには、このセクションの後半の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="81a7d-118">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81a7d-119">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span><span class="sxs-lookup"><span data-stu-id="81a7d-119">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="81a7d-120">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span><span class="sxs-lookup"><span data-stu-id="81a7d-120">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span>



</div>

<span data-ttu-id="81a7d-121">**False に設定した UseNormalizationRules**</span><span class="sxs-lookup"><span data-stu-id="81a7d-121">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="81a7d-122">**UseNormalizationRules**の値を False に設定して、ユーザーが Lync Server 2013 による正規化ルールの適用を行わずに Active Directory ドメインサービスで定義されているように電話番号を使用できるようにするには、 **UseNormalizationRules**と**Ignoregenericrules**パラメーターを True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81a7d-122">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Lync Server 2013 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="81a7d-123">これらのパラメーターを True に設定するには、このセクションの後半の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="81a7d-123">Follow the procedure later in this section to set these parameters to True.</span></span>

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="81a7d-124">アドレス帳のカスタマイズした正規化ルールを移行するには</span><span class="sxs-lookup"><span data-stu-id="81a7d-124">To migrate Address Book customized normalization rules</span></span>

1.  <span data-ttu-id="81a7d-125">会社の \_ 電話 \_ 番号の \_ 正規化 \_Rules.txt、アドレス帳の共有フォルダーのルートにあるファイルを検索し、それを Lync Server 2013 パイロットプールのアドレス帳の共有フォルダーのルートにコピーします。</span><span class="sxs-lookup"><span data-stu-id="81a7d-125">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="81a7d-126">アドレス帳の正規化ルールの例は、ABS Web コンポーネントのファイルディレクトリにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="81a7d-126">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="81a7d-127">パスは<STRONG>次のとおりです。 $installedDriveLetter: Files\Files\ の Lync Server 2013 \ Web Components\Address Book Sample_Company_Phone_Number_Normalization_Rules.txt、</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="81a7d-127">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="81a7d-128">このファイルは &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; 、アドレス帳の共有フォルダーのルートディレクトリに、Company_Phone_Number_Normalization_Rules.txtとしてコピーしたり名前を変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="81a7d-128">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="81a7d-129">たとえば、アドレス帳が<STRONG>$serverX</STRONG>で共有されている場合、この &nbsp; パスは<STRONG> \\ $serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>のようになります。</span><span class="sxs-lookup"><span data-stu-id="81a7d-129">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="81a7d-130">メモ帳などのテキストエディターを使用して、会社の \_ 電話 \_ 番号の \_ 正規化 \_Rules.txt ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="81a7d-130">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="81a7d-131">特定の種類のエントリは、Lync Server 2013 では正しく動作しません。</span><span class="sxs-lookup"><span data-stu-id="81a7d-131">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="81a7d-132">このファイルに目を通して、このステップで説明しているような種類のエントリがあれば、必要に応じてそれを編修し、パイロット プール内のアドレス帳共有フォルダーに変更後のファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="81a7d-132">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="81a7d-133">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span><span class="sxs-lookup"><span data-stu-id="81a7d-133">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="81a7d-134">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span><span class="sxs-lookup"><span data-stu-id="81a7d-134">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="81a7d-135">For example, the following string would cause the normalization rule to fail:</span><span class="sxs-lookup"><span data-stu-id="81a7d-135">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="81a7d-136">次の文字列では正規化ルールに問題は生じません。</span><span class="sxs-lookup"><span data-stu-id="81a7d-136">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="81a7d-137">UseNormalizationRules および IgnoreGenericRules を true に設定するには</span><span class="sxs-lookup"><span data-stu-id="81a7d-137">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1.  <span data-ttu-id="81a7d-138">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="81a7d-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="81a7d-139">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="81a7d-139">Do one of the following:</span></span>
    
      - <span data-ttu-id="81a7d-140">展開に Lync Server 2013 のみが含まれている場合は、グローバルレベルで次のコマンドレットを実行して、 **UseNormalizationRules**および**ignoregenericrules**の値を True に変更します。</span><span class="sxs-lookup"><span data-stu-id="81a7d-140">If your deployment includes only Lync Server 2013, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="81a7d-141">展開に Lync Server 2013 と Lync Server 2010 または Office Communications Server 2007 R2 の組み合わせが含まれている場合は、次のコマンドレットを実行して、トポロジ内の各 Lync Server 2013 プールに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="81a7d-141">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="81a7d-142">中央管理ストアのレプリケーションがすべてのプールで実行されるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="81a7d-142">Wait for Central Management store replication to occur on all pools.</span></span>

4.  <span data-ttu-id="81a7d-143">展開でコンテンツをクリアするために、電話の正規化ルールファイル "会社 \_ 電話 \_ 番号の \_ 正規化 \_Rules.txt" を変更します。</span><span class="sxs-lookup"><span data-stu-id="81a7d-143">Modify the phone normalization rules file, "Company\_Phone\_Number\_Normalization\_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="81a7d-144">ファイルは、各 Lync Server 2013 プールのファイル共有にあります。</span><span class="sxs-lookup"><span data-stu-id="81a7d-144">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="81a7d-145">ファイルが存在しない場合は、"会社 \_ 電話 \_ 番号の \_ 正規化Rules.txt" という名前の空のファイルを作成し \_ ます。</span><span class="sxs-lookup"><span data-stu-id="81a7d-145">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt".</span></span>

5.  <span data-ttu-id="81a7d-146">すべてのフロントエンドプールが新しいファイルを読み取るまで数分待機します。</span><span class="sxs-lookup"><span data-stu-id="81a7d-146">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="81a7d-147">展開内の各 Lync Server 2013 プールで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="81a7d-147">Run the following cmdlet on each Lync Server 2013 pool in your deployment:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

