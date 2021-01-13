---
title: Skype for Business Config.xmlインストール タスクを実行するには、このコマンドを使用します。
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: '概要: Config.xmlファイルを使用して、追加のインストール手順を指定する方法について説明します。'
ms.openlocfilehash: 1b8aeeb16e061e7816e475f01c9cd9a9146306ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825187"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="93999-103">Skype for Business Config.xmlを使用してインストール タスクを実行する</span><span class="sxs-lookup"><span data-stu-id="93999-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>

<span data-ttu-id="93999-104">**概要:** このファイルを使用してConfig.xml手順を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="93999-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>

<span data-ttu-id="93999-p101">Office カスタマイズ ツール (OCT) はカスタマイズ インストール向けの主要ツールですが、管理者は OCT では使用できない追加のインストール手順を Config.xml ファイルによって指定できます。以下のカスタマイズは、Config.xml ファイルを使用しないと実行できません。</span><span class="sxs-lookup"><span data-stu-id="93999-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

- <span data-ttu-id="93999-107">ネットワーク インストール ポイントのパスを指定する。</span><span class="sxs-lookup"><span data-stu-id="93999-107">Specify the path of the network installation point.</span></span>

- <span data-ttu-id="93999-108">インストールする製品を選択する。</span><span class="sxs-lookup"><span data-stu-id="93999-108">Select the products to install.</span></span>

- <span data-ttu-id="93999-109">ログ記録や、セットアップ カスタマイズ ファイルおよびソフトウェア更新プログラムの場所を構成する。</span><span class="sxs-lookup"><span data-stu-id="93999-109">Configure logging and the location of the Setup customization file and software updates.</span></span>

- <span data-ttu-id="93999-110">インストール オプション (ユーザー名など) を指定する。</span><span class="sxs-lookup"><span data-stu-id="93999-110">Specify installation options, such as user name.</span></span>

- <span data-ttu-id="93999-111">Office をインストールせずにローカル インストール ソース (LIS) をユーザーのコンピューターにコピーする。</span><span class="sxs-lookup"><span data-stu-id="93999-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

- <span data-ttu-id="93999-112">インストールに対して言語の追加または削除を行う。</span><span class="sxs-lookup"><span data-stu-id="93999-112">Add or remove languages from the installation.</span></span>

<span data-ttu-id="93999-113">Skype for Business のサイレント インストールを構成Config.xmlファイルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="93999-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 

<span data-ttu-id="93999-114">既定では、コアConfig.xmlフォルダーに格納されているファイル (\ product など) を指定 _します_。WW) は、セットアップに製品のインストールを指示します。</span><span class="sxs-lookup"><span data-stu-id="93999-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="93999-115">たとえば、次のフォルダーConfig.xmlファイルは Skype for Business をインストールします。</span><span class="sxs-lookup"><span data-stu-id="93999-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>

- <span data-ttu-id="93999-116">\\server\share\Skype15\Skype.WW \Config.xml</span><span class="sxs-lookup"><span data-stu-id="93999-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>

<span data-ttu-id="93999-117">次Config.xml Skype for Business のインストールで最も一般的に使用される次の要素の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="93999-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>

<span data-ttu-id="93999-118">**Config.xml の要素**</span><span class="sxs-lookup"><span data-stu-id="93999-118">**Config.xml elements**</span></span>


| <span data-ttu-id="93999-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="93999-119">**Element**</span></span>              | <span data-ttu-id="93999-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="93999-120">**Description**</span></span>                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="93999-121">構成</span><span class="sxs-lookup"><span data-stu-id="93999-121">Configuration</span></span>  <br/>     | <span data-ttu-id="93999-122">トップ レベルの要素 (必須)。</span><span class="sxs-lookup"><span data-stu-id="93999-122">Top-level element (required).</span></span> <span data-ttu-id="93999-123">Product 属性を含む。例: Product=Lync (これは Skype for Business クライアントで機能します)</span><span class="sxs-lookup"><span data-stu-id="93999-123">Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/>                                                                                                                                                          |
| <span data-ttu-id="93999-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="93999-124">OptionState</span></span>  <br/>       | <span data-ttu-id="93999-125">インストール中、特定の製品の機能が処理される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="93999-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="93999-126">Outlook に干渉する共有コンポーネントを含むBusiness Connectivity Servicesをインストールしないようにするには、次の属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="93999-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="93999-127">Id="LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="93999-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="93999-128">State="Absent"</span><span class="sxs-lookup"><span data-stu-id="93999-128">State="Absent"</span></span> <br/>  <span data-ttu-id="93999-129">Children="Force"</span><span class="sxs-lookup"><span data-stu-id="93999-129">Children="Force"</span></span> <br/> |
| <span data-ttu-id="93999-130">ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="93999-130">Display</span></span>  <br/>           | <span data-ttu-id="93999-p105">セットアップがユーザーに表示する UI のレベル。一般的には次の属性があります。</span><span class="sxs-lookup"><span data-stu-id="93999-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="93999-133">CompletionNotice="Yes"</span><span class="sxs-lookup"><span data-stu-id="93999-133">CompletionNotice="Yes"</span></span>                                                                                                                                                                                |
| <span data-ttu-id="93999-134">ログ記録</span><span class="sxs-lookup"><span data-stu-id="93999-134">Logging</span></span>  <br/>           | <span data-ttu-id="93999-p106">セットアップが実行するログ記録の種類のオプション。一般的には次の属性があります。</span><span class="sxs-lookup"><span data-stu-id="93999-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="93999-137">Type ="Off"</span><span class="sxs-lookup"><span data-stu-id="93999-137">Type ="Off"</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="93999-138">Setting</span><span class="sxs-lookup"><span data-stu-id="93999-138">Setting</span></span>  <br/>           | <span data-ttu-id="93999-p107">Windows インストーラーのプロパティの値を指定します。一般的には次の属性があります。</span><span class="sxs-lookup"><span data-stu-id="93999-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="93999-141">Setting Id=" *name*" (Windows インストーラー プロパティの名前)</span><span class="sxs-lookup"><span data-stu-id="93999-141">Setting Id=" *name*" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="93999-142">Value=" *値*" (プロパティに割り当てる値)</span><span class="sxs-lookup"><span data-stu-id="93999-142">Value=" *value*" (the value to assign to the property)</span></span>  <br/>                                                             |
| <span data-ttu-id="93999-143">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="93999-143">DistributionPoint</span></span>  <br/> | <span data-ttu-id="93999-p108">インストールを実行するネットワーク インストール ポイントの完全修飾パス</span><span class="sxs-lookup"><span data-stu-id="93999-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="93999-146">Location=" *path*"</span><span class="sxs-lookup"><span data-stu-id="93999-146">Location=" *path*"</span></span>  <br/>                                                                                                                                     |

<span data-ttu-id="93999-147">次の例は、Config.xml Skype for Business クライアントの一般的なサイレント インストールのファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="93999-147">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="93999-148">Config.xml ファイルを使用してインストールとOfficeタスクを実行する方法の詳細については、以下を参照してください [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514) 。</span><span class="sxs-lookup"><span data-stu-id="93999-148">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="93999-149">Config.xml ファイルをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="93999-149">To customize the Config.xml file</span></span>

1. <span data-ttu-id="93999-150">Notepad などのテキスト エディター ツールで Config.xml ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="93999-150">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2. <span data-ttu-id="93999-151">変更する要素を含む行に移動します。</span><span class="sxs-lookup"><span data-stu-id="93999-151">Locate the lines that contain the elements you want to change.</span></span>

3. <span data-ttu-id="93999-152">使用するサイレント オプションで要素のエントリを変更します。</span><span class="sxs-lookup"><span data-stu-id="93999-152">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="93999-153">コメント区切り記号 " " を必ず削除してください \<!--" and "--\> 。</span><span class="sxs-lookup"><span data-stu-id="93999-153">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="93999-154">たとえば、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="93999-154">For example, use the following syntax:</span></span>

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. <span data-ttu-id="93999-155">Config.xml ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="93999-155">Save the Config.xml file.</span></span>


