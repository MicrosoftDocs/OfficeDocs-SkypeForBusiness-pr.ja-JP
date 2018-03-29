---
title: Skype for Business Server 2015 で Config.xml を使用してインストール タスクを実行する
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Config.xml ファイルを使用して、追加のインストール手順の概要: 方法。'
ms.openlocfilehash: f55683d672df890be8baf0ac7ca50b3170faf3d2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-server-2015"></a><span data-ttu-id="3a190-103">Skype for Business Server 2015 で Config.xml を使用してインストール タスクを実行する</span><span class="sxs-lookup"><span data-stu-id="3a190-103">Use Config.xml to perform installation tasks in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3a190-104">**概要: ** Config.xml ファイルを使用して追加のインストール手順を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3a190-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>
  
<span data-ttu-id="3a190-p101">Office カスタマイズ ツール (OCT) はカスタマイズ インストール向けの主要ツールですが、管理者は OCT では使用できない追加のインストール手順を Config.xml ファイルによって指定できます。以下のカスタマイズは、Config.xml ファイルを使用しないと実行できません。</span><span class="sxs-lookup"><span data-stu-id="3a190-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>
  
- <span data-ttu-id="3a190-107">ネットワーク インストール ポイントのパスを指定する。</span><span class="sxs-lookup"><span data-stu-id="3a190-107">Specify the path of the network installation point.</span></span>
    
- <span data-ttu-id="3a190-108">インストールする製品を選択する。</span><span class="sxs-lookup"><span data-stu-id="3a190-108">Select the products to install.</span></span>
    
- <span data-ttu-id="3a190-109">ログ記録や、セットアップ カスタマイズ ファイルおよびソフトウェア更新プログラムの場所を構成する。</span><span class="sxs-lookup"><span data-stu-id="3a190-109">Configure logging and the location of the Setup customization file and software updates.</span></span>
    
- <span data-ttu-id="3a190-110">インストール オプション (ユーザー名など) を指定する。</span><span class="sxs-lookup"><span data-stu-id="3a190-110">Specify installation options, such as user name.</span></span>
    
- <span data-ttu-id="3a190-111">Office をインストールせずにローカル インストール ソース (LIS) をユーザーのコンピューターにコピーする。</span><span class="sxs-lookup"><span data-stu-id="3a190-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>
    
- <span data-ttu-id="3a190-112">インストールに対する言語の追加または削除を行う。</span><span class="sxs-lookup"><span data-stu-id="3a190-112">Add or remove languages from the installation.</span></span>
    
<span data-ttu-id="3a190-113">Config.xml ファイルを使用して、Skype をビジネスのサイレント インストールを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3a190-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 
  
<span data-ttu-id="3a190-114">既定では、コア製品フォルダーに格納されている Config.xml ファイル (たとえば、\_製品_です。WW) では、その製品をインストールするように指示します。</span><span class="sxs-lookup"><span data-stu-id="3a190-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="3a190-115">などの次のフォルダーにある Config.xml ファイルには、ビジネスの Skype がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3a190-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>
  
- <span data-ttu-id="3a190-116">\\server\share\Skype15\Skype.WW \Config.xml</span><span class="sxs-lookup"><span data-stu-id="3a190-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>
    
<span data-ttu-id="3a190-117">ビジネスのインストールのため Skype を最もよく使用される Config.xml の要素は、次の表に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a190-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>
  
<span data-ttu-id="3a190-118">**Config.xml の要素**</span><span class="sxs-lookup"><span data-stu-id="3a190-118">**Config.xml elements**</span></span>

|<span data-ttu-id="3a190-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="3a190-119">**Element**</span></span>|<span data-ttu-id="3a190-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="3a190-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3a190-121">Configuration</span><span class="sxs-lookup"><span data-stu-id="3a190-121">Configuration</span></span>  <br/> |<span data-ttu-id="3a190-p103">最上位レベルの要素 (必須)。製品属性が含まれます。例: Product=Lync (Skype for Business クライアントで使用されます)</span><span class="sxs-lookup"><span data-stu-id="3a190-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/> |
|<span data-ttu-id="3a190-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="3a190-124">OptionState</span></span>  <br/> | <span data-ttu-id="3a190-125">インストール中、特定の製品の機能が処理される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="3a190-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="3a190-126">Outlook 2016 の妨げになる共有コンポーネントが含まれている Business Connectivity Services のインストールを防ぐために次の属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="3a190-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook 2016:</span></span> <br/>  <span data-ttu-id="3a190-127">Id ="LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="3a190-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="3a190-128">State="Absent"</span><span class="sxs-lookup"><span data-stu-id="3a190-128">State="Absent"</span></span> <br/>  <span data-ttu-id="3a190-129">Children="Force"</span><span class="sxs-lookup"><span data-stu-id="3a190-129">Children="Force"</span></span> <br/> |
|<span data-ttu-id="3a190-130">Display</span><span class="sxs-lookup"><span data-stu-id="3a190-130">Display</span></span>  <br/> | <span data-ttu-id="3a190-p105">セットアップがユーザーに表示する UI のレベル。一般的には次の属性があります。</span><span class="sxs-lookup"><span data-stu-id="3a190-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="3a190-133">CompletionNotice =「はい」</span><span class="sxs-lookup"><span data-stu-id="3a190-133">CompletionNotice="Yes"</span></span> | <span data-ttu-id="3a190-134">」No"(default)</span><span class="sxs-lookup"><span data-stu-id="3a190-134">"No"(default)</span></span> <br/>  <span data-ttu-id="3a190-135">AcceptEula =「はい」</span><span class="sxs-lookup"><span data-stu-id="3a190-135">AcceptEula="Yes"</span></span> | <span data-ttu-id="3a190-136">」No"(default)</span><span class="sxs-lookup"><span data-stu-id="3a190-136">"No"(default)</span></span> <br/> |
|<span data-ttu-id="3a190-137">Logging</span><span class="sxs-lookup"><span data-stu-id="3a190-137">Logging</span></span>  <br/> | <span data-ttu-id="3a190-p106">セットアップが実行するログ記録の種類のオプション。一般的には次の属性があります。</span><span class="sxs-lookup"><span data-stu-id="3a190-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="3a190-140">タイプ ="Off"</span><span class="sxs-lookup"><span data-stu-id="3a190-140">Type ="Off"</span></span> | <span data-ttu-id="3a190-141">」Standard"(default)</span><span class="sxs-lookup"><span data-stu-id="3a190-141">"Standard"(default)</span></span> | <span data-ttu-id="3a190-142">「詳細」</span><span class="sxs-lookup"><span data-stu-id="3a190-142">"Verbose"</span></span> <br/>  <span data-ttu-id="3a190-143">テンプレート ="_ファイル名_.txt」(ログ ファイルの名前)</span><span class="sxs-lookup"><span data-stu-id="3a190-143">Template=" _filename_.txt" (the name of the log file)</span></span>  <br/> |
|<span data-ttu-id="3a190-144">Setting</span><span class="sxs-lookup"><span data-stu-id="3a190-144">Setting</span></span>  <br/> | <span data-ttu-id="3a190-p107">Windows インストーラーのプロパティの値を指定します。一般的には次の属性があります。</span><span class="sxs-lookup"><span data-stu-id="3a190-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="3a190-147">Id の設定 ="_名前_"(Windows インストーラー プロパティの名前)</span><span class="sxs-lookup"><span data-stu-id="3a190-147">Setting Id=" _name_" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="3a190-148">値 ="_値_"(プロパティに代入する値)</span><span class="sxs-lookup"><span data-stu-id="3a190-148">Value=" _value_" (the value to assign to the property)</span></span>  <br/> |
|<span data-ttu-id="3a190-149">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="3a190-149">DistributionPoint</span></span>  <br/> | <span data-ttu-id="3a190-p108">インストールを実行するネットワーク インストール ポイントの完全修飾パス</span><span class="sxs-lookup"><span data-stu-id="3a190-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="3a190-152">場所 ="_パス_"</span><span class="sxs-lookup"><span data-stu-id="3a190-152">Location=" _path_"</span></span>  <br/> |
   
<span data-ttu-id="3a190-153">次の例では、ビジネスの Skype の標準的なサイレント インストールの Config.xml ファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="3a190-153">The following example shows a Config.xml file for a typical silent installation of Skype for Business.</span></span> 
  
```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="3a190-154">Office のインストールとメンテナンス タスクを実行するのには Config.xml ファイルの使用に関する詳細情報は[https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)です。</span><span class="sxs-lookup"><span data-stu-id="3a190-154">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>
  
## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="3a190-155">Config.xml ファイルをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="3a190-155">To customize the Config.xml file</span></span>

1. <span data-ttu-id="3a190-156">Notepad などのテキスト エディター ツールで Config.xml ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3a190-156">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>
    
2. <span data-ttu-id="3a190-157">変更する要素を含む行に移動します。</span><span class="sxs-lookup"><span data-stu-id="3a190-157">Locate the lines that contain the elements you want to change.</span></span>
    
3. <span data-ttu-id="3a190-158">使用するサイレント オプションで要素のエントリを変更します。</span><span class="sxs-lookup"><span data-stu-id="3a190-158">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="3a190-159">コメント区切り記号を削除するかどうかを確認」\<!-"と"-\>」。</span><span class="sxs-lookup"><span data-stu-id="3a190-159">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="3a190-160">たとえば、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="3a190-160">For example, use the following syntax:</span></span>
    
  ```
  < DistributionPoint Location="\\server\share\Skype15" />
  ```

4. <span data-ttu-id="3a190-161">Config.xml ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="3a190-161">Save the Config.xml file.</span></span>
    

