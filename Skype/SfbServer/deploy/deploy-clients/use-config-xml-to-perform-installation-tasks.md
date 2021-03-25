---
title: Skype for business Config.xmlでインストール タスクを実行するには、次の手順を実行します。
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
ms.openlocfilehash: dbf4c4ba4e652f4b777e0c901fee4ffb0ad68af3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121141"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="74b8d-103">Skype for business Config.xmlでインストール タスクを実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="74b8d-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>

<span data-ttu-id="74b8d-104">**概要:** 追加のインストール手順を指定Config.xmlファイルを使用する方法。</span><span class="sxs-lookup"><span data-stu-id="74b8d-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>

<span data-ttu-id="74b8d-p101">Office カスタマイズ ツール (OCT) はカスタマイズ インストール向けの主要ツールですが、管理者は OCT では使用できない追加のインストール手順を Config.xml ファイルによって指定できます。以下のカスタマイズは、Config.xml ファイルを使用しないと実行できません。</span><span class="sxs-lookup"><span data-stu-id="74b8d-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

- <span data-ttu-id="74b8d-107">ネットワーク インストール ポイントのパスを指定する。</span><span class="sxs-lookup"><span data-stu-id="74b8d-107">Specify the path of the network installation point.</span></span>

- <span data-ttu-id="74b8d-108">インストールする製品を選択する。</span><span class="sxs-lookup"><span data-stu-id="74b8d-108">Select the products to install.</span></span>

- <span data-ttu-id="74b8d-109">ログ記録や、セットアップ カスタマイズ ファイルおよびソフトウェア更新プログラムの場所を構成する。</span><span class="sxs-lookup"><span data-stu-id="74b8d-109">Configure logging and the location of the Setup customization file and software updates.</span></span>

- <span data-ttu-id="74b8d-110">インストール オプション (ユーザー名など) を指定する。</span><span class="sxs-lookup"><span data-stu-id="74b8d-110">Specify installation options, such as user name.</span></span>

- <span data-ttu-id="74b8d-111">Office をインストールせずにローカル インストール ソース (LIS) をユーザーのコンピューターにコピーする。</span><span class="sxs-lookup"><span data-stu-id="74b8d-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

- <span data-ttu-id="74b8d-112">インストールに対して言語の追加または削除を行う。</span><span class="sxs-lookup"><span data-stu-id="74b8d-112">Add or remove languages from the installation.</span></span>

<span data-ttu-id="74b8d-113">Skype for Business サイレント インストールを構成するには、Config.xmlファイルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="74b8d-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 

<span data-ttu-id="74b8d-114">既定では、コアConfig.xmlに格納されているファイル (\製品など) を指定 _します_。WW) は、セットアップを指示して、その製品をインストールします。</span><span class="sxs-lookup"><span data-stu-id="74b8d-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="74b8d-115">たとえば、次のフォルダーConfig.xmlファイルは Skype for Business をインストールします。</span><span class="sxs-lookup"><span data-stu-id="74b8d-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>

- <span data-ttu-id="74b8d-116">\\server\share\Skype15\Skype.WW \Config.xml</span><span class="sxs-lookup"><span data-stu-id="74b8d-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>

<span data-ttu-id="74b8d-117">Skype for Business Config.xml最も一般的に使用される要素の一覧を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="74b8d-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>

<span data-ttu-id="74b8d-118">**Config.xml の要素**</span><span class="sxs-lookup"><span data-stu-id="74b8d-118">**Config.xml elements**</span></span>


| <span data-ttu-id="74b8d-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="74b8d-119">**Element**</span></span>              | <span data-ttu-id="74b8d-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="74b8d-120">**Description**</span></span>                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="74b8d-121">構成</span><span class="sxs-lookup"><span data-stu-id="74b8d-121">Configuration</span></span>  <br/>     | <span data-ttu-id="74b8d-122">トップ レベルの要素 (必須)。</span><span class="sxs-lookup"><span data-stu-id="74b8d-122">Top-level element (required).</span></span> <span data-ttu-id="74b8d-123">Product 属性 (Product=Lync など) が含まれる (これは Skype for Business クライアントで機能します)</span><span class="sxs-lookup"><span data-stu-id="74b8d-123">Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/>                                                                                                                                                          |
| <span data-ttu-id="74b8d-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="74b8d-124">OptionState</span></span>  <br/>       | <span data-ttu-id="74b8d-125">インストール中、特定の製品の機能が処理される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="74b8d-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="74b8d-126">Outlook に干渉する共有コンポーネントを含むBusiness Connectivity Servicesのインストールを防止するには、次の属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="74b8d-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="74b8d-127">Id="LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="74b8d-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="74b8d-128">State="Absent"</span><span class="sxs-lookup"><span data-stu-id="74b8d-128">State="Absent"</span></span> <br/>  <span data-ttu-id="74b8d-129">Children="Force"</span><span class="sxs-lookup"><span data-stu-id="74b8d-129">Children="Force"</span></span> <br/> |
| <span data-ttu-id="74b8d-130">ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="74b8d-130">Display</span></span>  <br/>           | <span data-ttu-id="74b8d-p105">セットアップがユーザーに表示する UI のレベル。一般的には次の属性があります。</span><span class="sxs-lookup"><span data-stu-id="74b8d-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="74b8d-133">CompletionNotice="Yes"</span><span class="sxs-lookup"><span data-stu-id="74b8d-133">CompletionNotice="Yes"</span></span>                                                                                                                                                                                |
| <span data-ttu-id="74b8d-134">ログ記録</span><span class="sxs-lookup"><span data-stu-id="74b8d-134">Logging</span></span>  <br/>           | <span data-ttu-id="74b8d-p106">セットアップが実行するログ記録の種類のオプション。一般的には次の属性があります。</span><span class="sxs-lookup"><span data-stu-id="74b8d-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="74b8d-137">Type ="Off"</span><span class="sxs-lookup"><span data-stu-id="74b8d-137">Type ="Off"</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="74b8d-138">Setting</span><span class="sxs-lookup"><span data-stu-id="74b8d-138">Setting</span></span>  <br/>           | <span data-ttu-id="74b8d-p107">Windows インストーラーのプロパティの値を指定します。一般的には次の属性があります。</span><span class="sxs-lookup"><span data-stu-id="74b8d-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="74b8d-141">Id=" *という名前を設定* する (Windows インストーラー プロパティの名前)</span><span class="sxs-lookup"><span data-stu-id="74b8d-141">Setting Id=" *name*" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="74b8d-142">Value=" *値*" (プロパティに割り当てる値)</span><span class="sxs-lookup"><span data-stu-id="74b8d-142">Value=" *value*" (the value to assign to the property)</span></span>  <br/>                                                             |
| <span data-ttu-id="74b8d-143">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="74b8d-143">DistributionPoint</span></span>  <br/> | <span data-ttu-id="74b8d-p108">インストールを実行するネットワーク インストール ポイントの完全修飾パス</span><span class="sxs-lookup"><span data-stu-id="74b8d-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="74b8d-146">Location=" *パス*"</span><span class="sxs-lookup"><span data-stu-id="74b8d-146">Location=" *path*"</span></span>  <br/>                                                                                                                                     |

<span data-ttu-id="74b8d-147">次の使用例は、skype for Business クライアントConfig.xmlサイレント インストールの一般的なファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="74b8d-147">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="74b8d-148">Config.xmlファイルを使用してインストールおよびOfficeタスクを実行する方法の詳細については、以下のページを参照してください [https://go.microsoft.com/fwlink/p/?linkid=267514](/previous-versions/office/office-2013-resource-kit/cc179195(v=office.15)) 。</span><span class="sxs-lookup"><span data-stu-id="74b8d-148">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](/previous-versions/office/office-2013-resource-kit/cc179195(v=office.15)).</span></span>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="74b8d-149">Config.xml ファイルをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="74b8d-149">To customize the Config.xml file</span></span>

1. <span data-ttu-id="74b8d-150">Notepad などのテキスト エディター ツールで Config.xml ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="74b8d-150">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2. <span data-ttu-id="74b8d-151">変更する要素を含む行に移動します。</span><span class="sxs-lookup"><span data-stu-id="74b8d-151">Locate the lines that contain the elements you want to change.</span></span>

3. <span data-ttu-id="74b8d-152">使用するサイレント オプションで要素のエントリを変更します。</span><span class="sxs-lookup"><span data-stu-id="74b8d-152">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="74b8d-153">コメント区切り記号 "" を削除してください \<!--" and "--\> 。</span><span class="sxs-lookup"><span data-stu-id="74b8d-153">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="74b8d-154">たとえば、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="74b8d-154">For example, use the following syntax:</span></span>

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. <span data-ttu-id="74b8d-155">Config.xml ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="74b8d-155">Save the Config.xml file.</span></span>