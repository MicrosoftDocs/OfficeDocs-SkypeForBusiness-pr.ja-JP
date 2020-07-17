---
title: アドレス帳を移行する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 通常、アドレス帳は他のトポロジと一緒に移行されます。 ただし、従来の環境で次のようにカスタマイズした場合は、移行後の手順を実行する必要があります。
ms.openlocfilehash: 6d2ccf0d38814d149495518a71f888f0c2999d24
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752839"
---
# <a name="migrate-address-book"></a><span data-ttu-id="c7237-104">アドレス帳を移行する</span><span class="sxs-lookup"><span data-stu-id="c7237-104">Migrate Address Book</span></span>

<span data-ttu-id="c7237-105">通常、アドレス帳は他のトポロジと一緒に移行されます。</span><span class="sxs-lookup"><span data-stu-id="c7237-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="c7237-106">ただし、従来の環境で次のようにカスタマイズした場合は、移行後の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7237-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="c7237-107">アドレス帳の正規化ルールをカスタマイズした場合。</span><span class="sxs-lookup"><span data-stu-id="c7237-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="c7237-108">**UseNormalizationRules** の既定の値を False に変更した場合。</span><span class="sxs-lookup"><span data-stu-id="c7237-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="c7237-109">**アドレス帳の正規化ルール**</span><span class="sxs-lookup"><span data-stu-id="c7237-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="c7237-110">従来の環境でアドレス帳の正規化ルールをカスタマイズした場合は、カスタマイズしたルールをパイロットプールに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7237-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="c7237-111">アドレス帳の正規化ルールをカスタマイズしていない場合は、アドレス帳サービスで移行するものは何もありません。</span><span class="sxs-lookup"><span data-stu-id="c7237-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="c7237-112">Skype for Business Server 2019 の既定の正規化ルールは、従来のインストールの既定のルールと同じです。</span><span class="sxs-lookup"><span data-stu-id="c7237-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="c7237-113">カスタマイズした正規化ルールを移行するには、このセクションの後半の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c7237-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="c7237-p104">組織でリモート通話コントロールを使用していて、アドレス帳の正規化ルールをカスタマイズした場合は、リモート通話コントロールを使う前に、このトピックの手順を遂行しなければなりません。この手順では、RTCUniversalServerAdmins グループのメンバーシップまたはそれに相当する権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="c7237-p104">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="c7237-116">**False に設定した UseNormalizationRules**</span><span class="sxs-lookup"><span data-stu-id="c7237-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="c7237-117">**UseNormalizationRules**の値を False に設定して、ユーザーが Skype For business Server 2019 を使用せずに Active Directory ドメインサービスで定義された電話番号を使用できるようにする場合は、 **UseNormalizationRules**および**Ignoregenericrules**パラメーターを True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7237-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="c7237-118">これらのパラメーターを True に設定するには、このセクションの後半の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c7237-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="c7237-119">アドレス帳のカスタマイズした正規化ルールを移行するには</span><span class="sxs-lookup"><span data-stu-id="c7237-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="c7237-120">アドレス帳の共有フォルダーのルートにある Company_Phone_Number_Normalization_Rules.txt ファイルを検索し、Skype for Business Server 2019 パイロットプールのアドレス帳共有フォルダーのルートにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c7237-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c7237-121">アドレス帳の正規化ルールの例は、ABS Web コンポーネントのファイルディレクトリにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="c7237-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="c7237-122">パスは **$installedDriveLetter: Files\Files\/Skype For Business Server 2019 \ Web Components\Address Book Sample_Company_Phone_Number_Normalization_Rules.txt**。</span><span class="sxs-lookup"><span data-stu-id="c7237-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="c7237-123">このファイルは、アドレス帳の共有フォルダーのルートディレクトリに、 **Company_Phone_Number_Normalization_Rules.txt**としてコピーしたり名前を変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="c7237-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="c7237-124">たとえば、アドレス帳が **$serverX**で共有されている場合、このパスは\*\* \\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*のようになります。</span><span class="sxs-lookup"><span data-stu-id="c7237-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="c7237-125">メモ帳などのテキスト エディターを使用して、Company_Phone_Number_Normalization_Rules.txt ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c7237-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="c7237-126">特定の種類のエントリは、Skype for Business Server 2019 では正しく動作しません。</span><span class="sxs-lookup"><span data-stu-id="c7237-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="c7237-127">このファイルに目を通して、このステップで説明しているような種類のエントリがあれば、必要に応じてそれを編修し、パイロット プール内のアドレス帳共有フォルダーに変更後のファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="c7237-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="c7237-p108">必要な空白文字や区切り文字が文字列に含まれていると、正規化ルールが正常に機能しなくなります。これらの文字は、正規化ルールに入力される文字列から取り除かれるためです。必要な空白文字や区切り文字が含まれる文字列を使用する場合は、文字列を編集する必要があります。たとえば、次の文字列を使用すると、正規化ルールが正常に機能しません。</span><span class="sxs-lookup"><span data-stu-id="c7237-p108">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:</span></span>

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="c7237-131">次の文字列では正規化ルールに問題は生じません。</span><span class="sxs-lookup"><span data-stu-id="c7237-131">The following string would not cause the normalization rule to fail:</span></span>

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="c7237-132">UseNormalizationRules および IgnoreGenericRules を true に設定するには</span><span class="sxs-lookup"><span data-stu-id="c7237-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="c7237-133">Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7237-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="c7237-134">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c7237-134">Do one of the following:</span></span>

   - <span data-ttu-id="c7237-135">展開に Skype for Business Server 2019 のみが含まれている場合は、グローバルレベルで次のコマンドレットを実行して、 **UseNormalizationRules**および**ignoregenericrules**の値を True に変更します。</span><span class="sxs-lookup"><span data-stu-id="c7237-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="c7237-136">展開に Skype for Business Server 2019 と従来のインストールの組み合わせが含まれている場合は、次のコマンドレットを実行して、トポロジ内の各 Skype for Business Server 2019 プールに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c7237-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="c7237-137">中央管理ストアのレプリケーションがすべてのプールで実行されるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="c7237-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="c7237-138">展開の電話正規化ルール ファイル "Company_Phone_Number_Normalization_Rules.txt" を変更し、コンテンツをクリアします。</span><span class="sxs-lookup"><span data-stu-id="c7237-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="c7237-139">このファイルは、各 Skype for Business Server 2019 プールのファイル共有にあります。</span><span class="sxs-lookup"><span data-stu-id="c7237-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="c7237-140">ファイルが存在しない場合は、"Company_Phone_Number_Normalization_Rules.txt" という名前の空のファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c7237-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="c7237-141">すべてのフロントエンドプールが新しいファイルを読み取るまで数分待機します。</span><span class="sxs-lookup"><span data-stu-id="c7237-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="c7237-142">展開の各 Skype for Business Server 2019 プールで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="c7237-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```PowerShell
   Update-CsAddressBook
   ```


