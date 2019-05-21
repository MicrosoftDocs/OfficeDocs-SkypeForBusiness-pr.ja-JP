---
title: アドレス帳の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 通常、アドレス帳は、他のトポロジと共に移行されます。 ただし、従来の環境で次のようにカスタマイズした場合は、移行後のいくつかの手順を実行する必要がある場合があります。
ms.openlocfilehash: 4263ae5bff60859cc9606a3683a3a03b0d2d4c35
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307120"
---
# <a name="migrate-address-book"></a><span data-ttu-id="a6424-104">アドレス帳の移行</span><span class="sxs-lookup"><span data-stu-id="a6424-104">Migrate Address Book</span></span>

<span data-ttu-id="a6424-105">通常、アドレス帳は、他のトポロジと共に移行されます。</span><span class="sxs-lookup"><span data-stu-id="a6424-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="a6424-106">ただし、従来の環境で次のようにカスタマイズした場合は、移行後のいくつかの手順を実行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a6424-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="a6424-107">アドレス帳の正規化規則をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="a6424-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="a6424-108">**UseNormalizationRules**パラメーターの既定値が False に変更されました。</span><span class="sxs-lookup"><span data-stu-id="a6424-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="a6424-109">**アドレス帳正規化ルール**</span><span class="sxs-lookup"><span data-stu-id="a6424-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="a6424-110">従来の環境でアドレス帳の正規化ルールをカスタマイズした場合は、カスタマイズしたルールをパイロットプールに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6424-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="a6424-111">アドレス帳の正規化ルールをカスタマイズしていない場合、アドレス帳サービスに移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="a6424-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="a6424-112">Skype for Business Server 2019 の既定の正規化ルールは、従来のインストールの既定の規則と同じです。</span><span class="sxs-lookup"><span data-stu-id="a6424-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="a6424-113">カスタマイズされた正規化ルールを移行するには、このセクションの後半の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a6424-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="a6424-114">組織でリモート通話コントロールを使用していて、アドレス帳正規化ルールをカスタマイズしている場合、リモート通話コントロールを使用する前に、このトピックの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6424-114">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="a6424-115">この手順では、RTCUniversalServerAdmins グループのメンバーシップ、または同等の権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="a6424-115">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="a6424-116">**UseNormalizationRules が False に設定**</span><span class="sxs-lookup"><span data-stu-id="a6424-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="a6424-117">ユーザーが Skype for Business Server \*\*\*\* 2019 で正規化ルールを**適用せずに Active Directory ドメインサービスで定義されているように、UseNormalizationRules の値を False に設定した場合、UseNormalizationRules**と**Ignoregenericrules**パラメーターを True にします。</span><span class="sxs-lookup"><span data-stu-id="a6424-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="a6424-118">このセクションの後半の手順に従って、これらのパラメーターを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="a6424-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="a6424-119">アドレス帳のカスタマイズされた正規化ルールを移行するには</span><span class="sxs-lookup"><span data-stu-id="a6424-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="a6424-120">アドレス帳の共有フォルダーのルートにある Company_Phone_Number_Normalization_Rules ファイルを見つけて、Skype for Business Server 2019 パイロットプールのアドレス帳の共有フォルダーのルートにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a6424-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a6424-121">サンプルのアドレス帳の正規化ルールは、ABS Web コンポーネントファイルディレクトリにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="a6424-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="a6424-122">パスは **$installedDriveLetter です。 Skype For Business Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules**をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a6424-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="a6424-123">このファイルは、 **Company_Phone_Number_Normalization_Rules**として、アドレス帳の共有フォルダーのルートディレクトリにコピーし、名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a6424-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="a6424-124">たとえば、 **$serverX**で共有されているアドレス帳は、 \*\* \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*のようなパスになります。</span><span class="sxs-lookup"><span data-stu-id="a6424-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="a6424-125">メモ帳などのテキストエディターを使用して、Company_Phone_Number_Normalization_Rules ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a6424-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="a6424-126">一部の種類のエントリは、Skype for Business Server 2019 では正しく動作しません。</span><span class="sxs-lookup"><span data-stu-id="a6424-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="a6424-127">この手順で説明したエントリの種類をファイルで確認し、必要に応じて編集して、変更内容をパイロットプールのアドレス帳の共有フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="a6424-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="a6424-128">必要な空白または句読点を含む文字列は、正規化ルールに入力された文字列から削除されるため、正規化ルールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="a6424-128">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="a6424-129">文字列に必要な空白または句読点が含まれている場合は、文字列を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6424-129">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="a6424-130">たとえば、次の文字列では正規化ルールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="a6424-130">For example, the following string would cause the normalization rule to fail:</span></span>

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="a6424-131">次の文字列では、正規化ルールが失敗することはありません。</span><span class="sxs-lookup"><span data-stu-id="a6424-131">The following string would not cause the normalization rule to fail:</span></span>

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="a6424-132">UseNormalizationRules と IgnoreGenericRules を true に設定するには</span><span class="sxs-lookup"><span data-stu-id="a6424-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="a6424-133">Skype for Business Server 管理シェルを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6424-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a6424-134">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a6424-134">Do one of the following:</span></span>

   - <span data-ttu-id="a6424-135">展開に Skype for Business Server 2019 のみが含まれている場合は、次のコマンドレットをグローバルレベルで実行して、 **UseNormalizationRules**と**ignoregenericrules**の値を True に変更します。</span><span class="sxs-lookup"><span data-stu-id="a6424-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="a6424-136">展開に Skype for Business Server 2019 とレガシインストールの組み合わせが含まれている場合は、次のコマンドレットを実行して、トポロジの各 Skype for Business Server 2019 プールに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a6424-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="a6424-137">すべてのプールで一元管理ストアのレプリケーションが実行されるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="a6424-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="a6424-138">コンテンツをクリアするために展開するために、電話の正規化規則ファイル "Company_Phone_Number_Normalization_Rules" を変更します。</span><span class="sxs-lookup"><span data-stu-id="a6424-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="a6424-139">ファイルは、各 Skype for Business Server 2019 プールのファイル共有にあります。</span><span class="sxs-lookup"><span data-stu-id="a6424-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="a6424-140">ファイルが存在しない場合は、"Company_Phone_Number_Normalization_Rules" という名前の空のファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6424-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="a6424-141">すべてのフロントエンドプールが新しいファイルを読み取るまで数分待ちます。</span><span class="sxs-lookup"><span data-stu-id="a6424-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="a6424-142">展開されている各 Skype for Business Server 2019 プールで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a6424-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```
   Update-CsAddressBook
   ```


