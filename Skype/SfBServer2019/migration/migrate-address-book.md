---
title: アドレス帳を移行します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 一般に、アドレス帳は、トポロジの残りの部分と共に移行されます。 ただし、レガシ環境で以下を設定している場合は、いくつかの移行後の手順を実行する必要があります。
ms.openlocfilehash: 081246acaaede37ab7f7f204a3f7204d9b25fbcc
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2019
ms.locfileid: "27788995"
---
# <a name="migrate-address-book"></a><span data-ttu-id="f4b81-104">アドレス帳を移行します。</span><span class="sxs-lookup"><span data-stu-id="f4b81-104">Migrate Address Book</span></span>

<span data-ttu-id="f4b81-105">一般に、アドレス帳は、トポロジの残りの部分と共に移行されます。</span><span class="sxs-lookup"><span data-stu-id="f4b81-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="f4b81-106">ただし、レガシ環境で以下を設定している場合は、いくつかの移行後の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4b81-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="f4b81-107">アドレス帳の正規化ルールをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="f4b81-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="f4b81-108">**UseNormalizationRules**パラメーターの既定値を False に変更します。</span><span class="sxs-lookup"><span data-stu-id="f4b81-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="f4b81-109">**アドレス帳の正規化の規則**</span><span class="sxs-lookup"><span data-stu-id="f4b81-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="f4b81-110">レガシ環境でアドレス帳の正規化の規則をカスタマイズした場合は、パイロット プールにカスタマイズされたルールを移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4b81-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="f4b81-111">場合はアドレス帳の正規化の規則をカスタマイズしていない、アドレス帳サービスに移行するものがあります。</span><span class="sxs-lookup"><span data-stu-id="f4b81-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="f4b81-112">ビジネス サーバー 2019 の Skype のデフォルトの正規化ルールは、従来のインストールの既定のルールと同じです。</span><span class="sxs-lookup"><span data-stu-id="f4b81-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="f4b81-113">カスタマイズされた正規化ルールを移行するには、このセクションで後述の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f4b81-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="f4b81-114">組織は、リモート通話コントロールを使用してアドレス帳の正規化ルールをカスタマイズする場合は、リモート通話コントロールを使用する前に、このトピックの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4b81-114">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="f4b81-115">プロシージャは、RTCUniversalServerAdmins グループまたは同等の権利のメンバーシップを必要とします。</span><span class="sxs-lookup"><span data-stu-id="f4b81-115">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="f4b81-116">**False に設定を UseNormalizationRules**</span><span class="sxs-lookup"><span data-stu-id="f4b81-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="f4b81-117">値を設定する**UseNormalizationRules**を false に定義されているとおり、ユーザーは電話番号を使用できるようにする場合は、ビジネス サーバー 2019 の Skype をせず、Active Directory ドメイン サービスは、正規化ルールを適用、**を設定する必要があります。UseNormalizationRules**および**IgnoreGenericRules**パラメーターを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="f4b81-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="f4b81-118">これらのパラメーターを True に設定するには、このセクションで後述の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f4b81-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="f4b81-119">アドレス帳を移行するのには、正規化ルールをカスタマイズしました。</span><span class="sxs-lookup"><span data-stu-id="f4b81-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="f4b81-120">アドレス帳の共有フォルダーのルートに Company_Phone_Number_Normalization_Rules.txt ファイルを検索して、ビジネス サーバー 2019 パイロット プールのため、Skype でアドレス帳の共有フォルダーのルートにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f4b81-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f4b81-121">サンプルのアドレス帳の正規化規則は、ABS の Web コンポーネントのファイル ディレクトリにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="f4b81-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="f4b81-122">パスは、 **$installedDriveLetter: \Program Files\Microsoft Skype ビジネス サーバー 2019\Web Components\Address 帳 Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt の**です。</span><span class="sxs-lookup"><span data-stu-id="f4b81-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="f4b81-123">このファイルをコピー、 **Company_Phone_Number_Normalization_Rules.txt**として、アドレス帳の共有フォルダーのルート ディレクトリに名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f4b81-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="f4b81-124">たとえば、 **$serverX**内の共有アドレス帳のパスようになります: \*\* \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*。</span><span class="sxs-lookup"><span data-stu-id="f4b81-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="f4b81-125">Company_Phone_Number_Normalization_Rules.txt ファイルを開くには、メモ帳などのテキスト エディターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4b81-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="f4b81-126">エントリの特定の種類が正しく動作しない Skype のビジネス サーバー 2019 の。</span><span class="sxs-lookup"><span data-stu-id="f4b81-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="f4b81-127">この手順で説明されているエントリの種類のファイルを参照、必要に応じて編集して、パイロット、プール内のアドレス帳の共有フォルダーに変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="f4b81-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="f4b81-128">含む文字列を必要な空白文字または句読点原因正規化の規則がこれらの文字は、正規化の規則に入力される文字列を取り除くために失敗します。</span><span class="sxs-lookup"><span data-stu-id="f4b81-128">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="f4b81-129">必要な空白文字または句読点を含む文字列を使っている場合、文字列を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4b81-129">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="f4b81-130">たとえば、次の文字列では、正規化ルールが失敗するが発生。</span><span class="sxs-lookup"><span data-stu-id="f4b81-130">For example, the following string would cause the normalization rule to fail:</span></span>

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="f4b81-131">次の文字列は、正規化ルールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="f4b81-131">The following string would not cause the normalization rule to fail:</span></span>

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="f4b81-132">UseNormalizationRules と IgnoreGenericRules を true に設定するには</span><span class="sxs-lookup"><span data-stu-id="f4b81-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="f4b81-133">ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネス サーバー 2019 の Skype をマイクロソフト**をクリック**ビジネス サーバー管理シェルの Skype**です。</span><span class="sxs-lookup"><span data-stu-id="f4b81-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="f4b81-134">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f4b81-134">Do one of the following:</span></span>

   - <span data-ttu-id="f4b81-135">展開には、ビジネス サーバー 2019 の Skype のみが含まれている場合を True に**UseNormalizationRules**と**IgnoreGenericRules**の値を変更するのにはグローバル レベルで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f4b81-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="f4b81-136">展開には、ビジネス サーバー 2019 およびレガシー インストールの Skype の組み合わせが含まれている場合は、次のコマンドレットを実行し、ビジネス サーバー 2019 のプール トポロジ内の各 Skype を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f4b81-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="f4b81-137">中央管理ストアのレプリケーションのすべてのプールで発生するを待ちます。</span><span class="sxs-lookup"><span data-stu-id="f4b81-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="f4b81-138">電話正規化ルールのファイル、コンテンツをクリアするのには、展開に「Company_Phone_Number_Normalization_Rules.txt」、を変更します。</span><span class="sxs-lookup"><span data-stu-id="f4b81-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="f4b81-139">ビジネス サーバー 2019 プールの各 Skype のファイル共有のファイルでは。</span><span class="sxs-lookup"><span data-stu-id="f4b81-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f4b81-140">ファイルが存在しない場合は、"Company_Phone_Number_Normalization_Rules.txt"という名前の空のファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f4b81-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="f4b81-141">新しいファイルを読み取るためのすべてのフロント エンド プールの数分間待機します。</span><span class="sxs-lookup"><span data-stu-id="f4b81-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="f4b81-142">ビジネス サーバー 2019 プールの展開では、各 Skype では、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f4b81-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```
   Update-CsAddressBook
   ```


