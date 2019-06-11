---
title: アドレス帳の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2293b7ad3e5ac14071bae4d5ecb935c24cfbb335
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="07fcf-102">アドレス帳の移行</span><span class="sxs-lookup"><span data-stu-id="07fcf-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07fcf-103">_**最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="07fcf-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="07fcf-104">一般に、Lync Server 2010 アドレス帳は、他のトポロジと共に移行されます。</span><span class="sxs-lookup"><span data-stu-id="07fcf-104">In general, the Lync Server 2010 Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="07fcf-105">ただし、Lync Server 2010 環境で次のようにカスタマイズした場合は、移行後にいくつかの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07fcf-105">However, you might need to perform some post-migration steps if you customized the following in your Lync Server 2010 environment:</span></span>

  - <span data-ttu-id="07fcf-106">**Partitionbyou** WMI プロパティを組織単位 (ou) ごとにグループのアドレス帳エントリに設定します。</span><span class="sxs-lookup"><span data-stu-id="07fcf-106">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span>

  - <span data-ttu-id="07fcf-107">アドレス帳の正規化規則をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="07fcf-107">Customized the Address Book normalization rules.</span></span>

  - <span data-ttu-id="07fcf-108">**UseNormalizationRules**パラメーターの既定値が False に変更されました。</span><span class="sxs-lookup"><span data-stu-id="07fcf-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span>

<span data-ttu-id="07fcf-109">**グループ化されたアドレス帳のエントリ**</span><span class="sxs-lookup"><span data-stu-id="07fcf-109">**Grouped Address Book Entries**</span></span>

<span data-ttu-id="07fcf-110">**Partitionbyou** WMI プロパティを True に設定して、各組織のアドレス帳を作成する場合、アドレス帳エントリのグループ化を続けたい場合は、ユーザーと連絡先に対して**Msrtcsip-userenabled true-groupingid** Active Directory 属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07fcf-110">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries.</span></span> <span data-ttu-id="07fcf-111">アドレス帳の検索の範囲を制限するために、アドレス帳のエントリをグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="07fcf-111">You might want to group address book entries to limit the scope of Address Book searches.</span></span> <span data-ttu-id="07fcf-112">**Msrtcsip-userenabled true-GroupingId**属性を使用するには、属性を設定するスクリプトを作成し、グループ化するすべてのユーザーに同じ値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="07fcf-112">To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together.</span></span> <span data-ttu-id="07fcf-113">たとえば、OU 内のすべてのユーザーに1つの値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="07fcf-113">For example, assign a single value for all the users in an OU.</span></span>

<span data-ttu-id="07fcf-114">**アドレス帳正規化ルール**</span><span class="sxs-lookup"><span data-stu-id="07fcf-114">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="07fcf-115">Lync Server 2010 環境でアドレス帳の正規化ルールをカスタマイズした場合は、カスタマイズしたルールをパイロットプールに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07fcf-115">If you customized Address Book normalization rules in your Lync Server 2010 environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="07fcf-116">アドレス帳の正規化ルールをカスタマイズしていない場合、アドレス帳サービスに移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="07fcf-116">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="07fcf-117">Lync Server 2013 の既定の正規化ルールは、Lync Server 2010 の既定のルールと同じです。</span><span class="sxs-lookup"><span data-stu-id="07fcf-117">The default normalization rules for Lync Server 2013 are the same as the default rules for Lync Server 2010.</span></span> <span data-ttu-id="07fcf-118">カスタマイズされた正規化ルールを移行するには、このセクションの後半の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="07fcf-118">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07fcf-119">組織でリモート通話コントロールを使用していて、アドレス帳正規化ルールをカスタマイズしている場合、リモート通話コントロールを使用する前に、このトピックの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07fcf-119">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="07fcf-120">この手順では、RTCUniversalServerAdmins グループのメンバーシップ、または同等の権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="07fcf-120">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span>



</div>

<span data-ttu-id="07fcf-121">**UseNormalizationRules が False に設定**</span><span class="sxs-lookup"><span data-stu-id="07fcf-121">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="07fcf-122">ユーザーが電話番号を使用できるように、 **UseNormalizationRules**の値を False に設定した場合、Lync Server 2013 で正規化ルールを適用することなく、Active Directory ドメインサービスで定義された電話番号を使用できるようにするには、UseNormalizationRules を設定する必要があります。 \*\*\*\* **Ignoregenericrules**パラメーターを True にします。</span><span class="sxs-lookup"><span data-stu-id="07fcf-122">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Lync Server 2013 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="07fcf-123">このセクションの後半の手順に従って、これらのパラメーターを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="07fcf-123">Follow the procedure later in this section to set these parameters to True.</span></span>

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="07fcf-124">アドレス帳のカスタマイズされた正規化ルールを移行するには</span><span class="sxs-lookup"><span data-stu-id="07fcf-124">To migrate Address Book customized normalization rules</span></span>

1.  <span data-ttu-id="07fcf-125">アドレス帳の\_共有\_フォルダー\_の\_ルートにある [会社電話番号の正規化ルール] .txt ファイルを見つけて、Lync Server 2013 パイロットプールのアドレス帳の共有フォルダーのルートにコピーします。</span><span class="sxs-lookup"><span data-stu-id="07fcf-125">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="07fcf-126">サンプルのアドレス帳の正規化ルールは、ABS Web コンポーネントファイルディレクトリにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="07fcf-126">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="07fcf-127">パスは<STRONG>$installedDriveLetter: Components\Address/Lync Server 2013 \ Web Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules、</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="07fcf-127">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="07fcf-128">このファイルは、 &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules</STRONG> &nbsp;として、アドレス帳の共有フォルダーのルートディレクトリにコピーし、名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="07fcf-128">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="07fcf-129">たとえば、 <STRONG>$serverX</STRONG>&nbsp;で共有されているアドレス帳は、 <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>のようなパスになります。</span><span class="sxs-lookup"><span data-stu-id="07fcf-129">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="07fcf-130">メモ帳などのテキストエディターを使用して、\_会社電話\_番号\_の正規化\_ルールの .txt ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="07fcf-130">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="07fcf-131">Lync Server 2013 では、特定の種類のエントリが正しく動作しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="07fcf-131">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="07fcf-132">この手順で説明したエントリの種類をファイルで確認し、必要に応じて編集して、変更内容をパイロットプールのアドレス帳の共有フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="07fcf-132">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="07fcf-133">必要な空白または句読点を含む文字列は、正規化ルールに入力された文字列から削除されるため、正規化ルールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="07fcf-133">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="07fcf-134">文字列に必要な空白または句読点が含まれている場合は、文字列を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07fcf-134">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="07fcf-135">たとえば、次の文字列では正規化ルールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="07fcf-135">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="07fcf-136">次の文字列では、正規化ルールが失敗することはありません。</span><span class="sxs-lookup"><span data-stu-id="07fcf-136">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="07fcf-137">UseNormalizationRules と IgnoreGenericRules を true に設定するには</span><span class="sxs-lookup"><span data-stu-id="07fcf-137">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1.  <span data-ttu-id="07fcf-138">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="07fcf-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="07fcf-139">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="07fcf-139">Do one of the following:</span></span>
    
      - <span data-ttu-id="07fcf-140">展開に Lync Server 2013 のみが含まれている場合、次のコマンドレットをグローバルレベルで実行して、 **UseNormalizationRules**と**ignoregenericrules**の値を True に変更します。</span><span class="sxs-lookup"><span data-stu-id="07fcf-140">If your deployment includes only Lync Server 2013, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="07fcf-141">展開に Lync Server 2013 および Lync Server 2010 または Office Communications Server 2007 R2 の組み合わせが含まれている場合は、次のコマンドレットを実行して、トポロジの各 Lync Server 2013 プールに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="07fcf-141">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="07fcf-142">すべてのプールで一元管理ストアのレプリケーションが実行されるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="07fcf-142">Wait for Central Management store replication to occur on all pools.</span></span>

4.  <span data-ttu-id="07fcf-143">コンテンツをクリアするために展開するに\_は\_、\_[\_電話の正規化ルールファイル] を変更します。</span><span class="sxs-lookup"><span data-stu-id="07fcf-143">Modify the phone normalization rules file, "Company\_Phone\_Number\_Normalization\_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="07fcf-144">ファイルは、各 Lync Server 2013 プールのファイル共有にあります。</span><span class="sxs-lookup"><span data-stu-id="07fcf-144">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="07fcf-145">ファイルが表示されていない場合は、"\_会社電話\_番号\_の正規化\_ルール .txt" という名前の空のファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="07fcf-145">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt".</span></span>

5.  <span data-ttu-id="07fcf-146">すべてのフロントエンドプールが新しいファイルを読み取るまで数分待ちます。</span><span class="sxs-lookup"><span data-stu-id="07fcf-146">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="07fcf-147">展開の各 Lync Server 2013 プールで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="07fcf-147">Run the following cmdlet on each Lync Server 2013 pool in your deployment:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

