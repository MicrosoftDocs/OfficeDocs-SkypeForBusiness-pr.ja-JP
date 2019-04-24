---
title: Config.xml を使用して、Skype のビジネスのクライアントのインストール ・ タスクを実行するのには
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: '概要:  Config.xml ファイルを使用して追加のインストール手順を指定する方法について説明します。'
ms.openlocfilehash: dfb6625146261b1bbf22e0f563717899c68beaae
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214850"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="4afdd-103">Config.xml を使用して、Skype のビジネスのクライアントのインストール ・ タスクを実行するのには</span><span class="sxs-lookup"><span data-stu-id="4afdd-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>

<span data-ttu-id="4afdd-104">\*\*概要: \*\* Config.xml ファイルを使用して追加のインストール手順を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4afdd-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>

<span data-ttu-id="4afdd-p101">Office カスタマイズ ツール (OCT) はカスタマイズ インストール向けの主要ツールですが、管理者は OCT では使用できない追加のインストール手順を Config.xml ファイルによって指定できます。以下のカスタマイズは、Config.xml ファイルを使用しないと実行できません。</span><span class="sxs-lookup"><span data-stu-id="4afdd-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

- <span data-ttu-id="4afdd-107">ネットワーク インストール ポイントのパスを指定する。</span><span class="sxs-lookup"><span data-stu-id="4afdd-107">Specify the path of the network installation point.</span></span>

- <span data-ttu-id="4afdd-108">インストールする製品を選択する。</span><span class="sxs-lookup"><span data-stu-id="4afdd-108">Select the products to install.</span></span>

- <span data-ttu-id="4afdd-109">ログ記録や、セットアップ カスタマイズ ファイルおよびソフトウェア更新プログラムの場所を構成する。</span><span class="sxs-lookup"><span data-stu-id="4afdd-109">Configure logging and the location of the Setup customization file and software updates.</span></span>

- <span data-ttu-id="4afdd-110">インストール オプション (ユーザー名など) を指定する。</span><span class="sxs-lookup"><span data-stu-id="4afdd-110">Specify installation options, such as user name.</span></span>

- <span data-ttu-id="4afdd-111">Office をインストールせずにローカル インストール ソース (LIS) をユーザーのコンピューターにコピーする。</span><span class="sxs-lookup"><span data-stu-id="4afdd-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

- <span data-ttu-id="4afdd-112">インストールに対する言語の追加または削除を行う。</span><span class="sxs-lookup"><span data-stu-id="4afdd-112">Add or remove languages from the installation.</span></span>

<span data-ttu-id="4afdd-113">Config.xml ファイルを使用して、Skype をビジネスのサイレント インストールを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4afdd-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 

<span data-ttu-id="4afdd-114">既定では、コア製品フォルダーに格納されている Config.xml ファイル (たとえば、\_製品_です。WW) では、その製品をインストールするように指示します。</span><span class="sxs-lookup"><span data-stu-id="4afdd-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="4afdd-115">などの次のフォルダーにある Config.xml ファイルには、ビジネスの Skype がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4afdd-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>

- <span data-ttu-id="4afdd-116">\\server\share\Skype15\Skype.WW \Config.xml</span><span class="sxs-lookup"><span data-stu-id="4afdd-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>

<span data-ttu-id="4afdd-117">ビジネスのインストールのため Skype を最もよく使用される Config.xml の要素は、次の表に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4afdd-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>

<span data-ttu-id="4afdd-118">**Config.xml の要素**</span><span class="sxs-lookup"><span data-stu-id="4afdd-118">**Config.xml elements**</span></span>


| <span data-ttu-id="4afdd-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="4afdd-119">**Element**</span></span>              | <span data-ttu-id="4afdd-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="4afdd-120">**Description**</span></span>                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="4afdd-121">Configuration</span><span class="sxs-lookup"><span data-stu-id="4afdd-121">Configuration</span></span>  <br/>     | <span data-ttu-id="4afdd-p103">最上位レベルの要素 (必須)。製品属性が含まれます。例: Product=Lync (Skype for Business クライアントで使用されます)</span><span class="sxs-lookup"><span data-stu-id="4afdd-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/>                                                                                                                                                          |
| <span data-ttu-id="4afdd-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="4afdd-124">OptionState</span></span>  <br/>       | <span data-ttu-id="4afdd-125">インストール中、特定の製品の機能が処理される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="4afdd-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="4afdd-126">干渉する Outlook の共有コンポーネントが含まれている Business Connectivity Services のインストールを防ぐために次の属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="4afdd-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="4afdd-127">Id="LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="4afdd-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="4afdd-128">State="Absent"</span><span class="sxs-lookup"><span data-stu-id="4afdd-128">State="Absent"</span></span> <br/>  <span data-ttu-id="4afdd-129">Children="Force"</span><span class="sxs-lookup"><span data-stu-id="4afdd-129">Children="Force"</span></span> <br/> |
| <span data-ttu-id="4afdd-130">Display</span><span class="sxs-lookup"><span data-stu-id="4afdd-130">Display</span></span>  <br/>           | <span data-ttu-id="4afdd-p105">セットアップがユーザーに表示する UI のレベル。一般的には次の属性があります。</span><span class="sxs-lookup"><span data-stu-id="4afdd-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="4afdd-133">CompletionNotice =「はい」</span><span class="sxs-lookup"><span data-stu-id="4afdd-133">CompletionNotice="Yes"</span></span>                                                                                                                                                                                |
| <span data-ttu-id="4afdd-134">Logging</span><span class="sxs-lookup"><span data-stu-id="4afdd-134">Logging</span></span>  <br/>           | <span data-ttu-id="4afdd-p106">セットアップが実行するログ記録の種類のオプション。一般的には次の属性があります。</span><span class="sxs-lookup"><span data-stu-id="4afdd-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="4afdd-137">タイプ ="Off"</span><span class="sxs-lookup"><span data-stu-id="4afdd-137">Type ="Off"</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="4afdd-138">Setting</span><span class="sxs-lookup"><span data-stu-id="4afdd-138">Setting</span></span>  <br/>           | <span data-ttu-id="4afdd-p107">Windows インストーラーのプロパティの値を指定します。一般的には次の属性があります。</span><span class="sxs-lookup"><span data-stu-id="4afdd-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="4afdd-141">Id の設定 ="*名前*"(Windows インストーラー プロパティの名前)</span><span class="sxs-lookup"><span data-stu-id="4afdd-141">Setting Id=" *name*" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="4afdd-142">値 ="*値*"(プロパティに代入する値)</span><span class="sxs-lookup"><span data-stu-id="4afdd-142">Value=" *value*" (the value to assign to the property)</span></span>  <br/>                                                             |
| <span data-ttu-id="4afdd-143">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="4afdd-143">DistributionPoint</span></span>  <br/> | <span data-ttu-id="4afdd-p108">インストールを実行するネットワーク インストール ポイントの完全修飾パス</span><span class="sxs-lookup"><span data-stu-id="4afdd-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="4afdd-146">場所 ="*パス*"</span><span class="sxs-lookup"><span data-stu-id="4afdd-146">Location=" *path*"</span></span>  <br/>                                                                                                                                     |

<span data-ttu-id="4afdd-147">ビジネス クライアント用の Skype の場合は、標準的なサイレント インストール用の Config.xml ファイルを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="4afdd-147">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 

```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="4afdd-148">Office のインストールとメンテナンス タスクを実行するのには Config.xml ファイルの使用に関する詳細情報は[https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)です。</span><span class="sxs-lookup"><span data-stu-id="4afdd-148">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="4afdd-149">Config.xml ファイルをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="4afdd-149">To customize the Config.xml file</span></span>

1. <span data-ttu-id="4afdd-150">Notepad などのテキスト エディター ツールで Config.xml ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4afdd-150">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2. <span data-ttu-id="4afdd-151">変更する要素を含む行に移動します。</span><span class="sxs-lookup"><span data-stu-id="4afdd-151">Locate the lines that contain the elements you want to change.</span></span>

3. <span data-ttu-id="4afdd-152">使用するサイレント オプションで要素のエントリを変更します。</span><span class="sxs-lookup"><span data-stu-id="4afdd-152">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="4afdd-153">コメント区切り記号を削除するかどうかを確認」\<!-"と"-\>」。</span><span class="sxs-lookup"><span data-stu-id="4afdd-153">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="4afdd-154">たとえば、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="4afdd-154">For example, use the following syntax:</span></span>

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. <span data-ttu-id="4afdd-155">Config.xml ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="4afdd-155">Save the Config.xml file.</span></span>


