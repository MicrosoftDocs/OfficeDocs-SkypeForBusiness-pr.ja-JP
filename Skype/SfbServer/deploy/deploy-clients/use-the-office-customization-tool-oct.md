---
title: Skype for Business Server で Office カスタマイズツール (OCT) を使用する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: '概要: Skype for Business クライアントで Office カスタマイズツールを使用する方法について説明します。'
ms.openlocfilehash: a71ab8947d964dff90510257c4a8b2cbffb3be96
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306203"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="09c48-103">Skype for Business Server で Office カスタマイズツール (OCT) を使用する</span><span class="sxs-lookup"><span data-stu-id="09c48-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="09c48-104">**概要:** Skype for Business クライアントで Office カスタマイズツールを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="09c48-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="09c48-105">Office カスタマイズ ツール (OCT) はセットアップ プログラムの一部であり、多くのカスタマイズにおける推奨ツールになっています。</span><span class="sxs-lookup"><span data-stu-id="09c48-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="09c48-106">OCT を使用して Office をカスタマイズし、カスタマイズ内容をセットアップ カスタマイズ (.msp) ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="09c48-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="09c48-107">そのファイルをネットワーク インストール ポイントの Updates フォルダーに配置します。</span><span class="sxs-lookup"><span data-stu-id="09c48-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="09c48-108">Office をインストールするときに、セットアップは Updates フォルダーのセットアップ カスタマイズ ファイルを検索し、カスタマイズ内容を適用します。</span><span class="sxs-lookup"><span data-stu-id="09c48-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="09c48-109">Updates フォルダーは、Office の最初のインストール中にソフトウェアの更新プログラムを展開するためにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="09c48-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="09c48-110">OCT はセットアップの一部であり、ボリュームライセンス版の製品でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="09c48-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="09c48-111">Office のソースファイルが含ま`setup.exe /admin`れているネットワークインストールポイントのルートからコマンドラインを入力して、OCT を実行します。</span><span class="sxs-lookup"><span data-stu-id="09c48-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="09c48-112">たとえば、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="09c48-112">For example, use the following:</span></span>
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="09c48-113">管理者は、OCT を使用して、セットアップカスタマイズの .msp ファイルを作成し、次の領域をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="09c48-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="09c48-114">**セットアップ**クライアントと既定の組織名、追加のネットワークインストールソース、プロダクトキー、エンドユーザーライセンス契約、表示レベル、以前のバージョンの Office を削除するための既定のインストール場所を指定するために使用されます。インストール、セキュリティ設定、セットアッププロパティ。</span><span class="sxs-lookup"><span data-stu-id="09c48-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="09c48-115">**機能**ユーザー設定を構成し、Office 機能のインストール方法をカスタマイズするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="09c48-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="09c48-116">管理者は、OCT を使用して、ユーザーの Office アプリケーション設定の初期既定値を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="09c48-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="09c48-117">ユーザーはインストール後にほとんどの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="09c48-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="09c48-118">**追加コンテンツ**ファイルを追加または削除したり、レジストリエントリを追加または削除したり、ショートカットを構成したりするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="09c48-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="09c48-119">**Outlook**ユーザーの既定の Outlook プロファイルのカスタマイズ、Exchange 設定の指定、アカウントの追加、アカウントの削除と設定のエクスポート、Send\Receive グループの指定を行うために使用されます。</span><span class="sxs-lookup"><span data-stu-id="09c48-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="09c48-120">OCT の詳細については、「 [oct を使用して Office 2013 をカスタマイズする](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09c48-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="09c48-121">この情報は、新しいバージョンの Office にも適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="09c48-121">Note that this information also applies to later versions of Office.</span></span>
  

