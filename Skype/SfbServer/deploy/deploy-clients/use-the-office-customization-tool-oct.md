---
title: Skype for Business Server Officeカスタマイズ ツール (OCT) を使用する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: '概要: Skype for Business クライアントOfficeカスタマイズ ツールを使用する方法について説明します。'
ms.openlocfilehash: 32cd7951690ce5b1e38c20d83c8f53a9c48cd19c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100453"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="aa3ae-103">Skype for Business Server Officeカスタマイズ ツール (OCT) を使用する</span><span class="sxs-lookup"><span data-stu-id="aa3ae-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="aa3ae-104">**概要:** Skype for Business クライアントOfficeカスタマイズ ツールを使用する方法。</span><span class="sxs-lookup"><span data-stu-id="aa3ae-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="aa3ae-105">カスタム Office (OCT) はセットアップ プログラムの一部であり、多くのカスタマイズに推奨されるツールです。</span><span class="sxs-lookup"><span data-stu-id="aa3ae-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="aa3ae-106">OCT を使用して、ユーザー設定Officeカスタマイズをセットアップ カスタマイズ .msp ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="aa3ae-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="aa3ae-107">ネットワーク インストール ポイントの [更新プログラム] フォルダーにファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="aa3ae-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="aa3ae-108">このファイルをインストールOfficeセットアップは、[更新プログラム] フォルダーでセットアップ カスタマイズ ファイルを検索し、カスタマイズを適用します。</span><span class="sxs-lookup"><span data-stu-id="aa3ae-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="aa3ae-109">Updates フォルダーは、ソフトウェア更新プログラムを初期インストール時に展開する場合にのみ使用Office。</span><span class="sxs-lookup"><span data-stu-id="aa3ae-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="aa3ae-110">OCT はセットアップの一部であり、ボリューム ライセンスバージョンの製品にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="aa3ae-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="aa3ae-111">OCT を実行するには、ソース ファイルを含むネットワーク インストール ポイントのルートからコマンド ライン  `setup.exe /admin` Officeします。</span><span class="sxs-lookup"><span data-stu-id="aa3ae-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="aa3ae-112">たとえば、次の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa3ae-112">For example, use the following:</span></span>
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="aa3ae-113">管理者は OCT を使用してセットアップ カスタマイズ .msp ファイルを作成し、次の領域をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="aa3ae-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="aa3ae-114">**セットアップ** クライアントと既定の組織名、追加のネットワーク インストール ソース、プロダクト キー、エンド ユーザー ライセンス契約、表示レベル、削除する以前のバージョンの Office、インストール中に実行するカスタム プログラム、セキュリティ設定、セットアップ プロパティを指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="aa3ae-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="aa3ae-115">**機能** ユーザー設定の構成および機能のインストール方法Office使用します。</span><span class="sxs-lookup"><span data-stu-id="aa3ae-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="aa3ae-116">管理者は OCT を使用して、ユーザーのアプリケーション設定Office既定の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="aa3ae-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="aa3ae-117">ユーザーはインストール後に大部分の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="aa3ae-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="aa3ae-118">**その他のコンテンツ** ファイルの追加または削除、レジストリ エントリの追加または削除、ショートカットの構成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="aa3ae-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="aa3ae-119">**Outlook** ユーザーの既定の Outlook プロファイルのカスタマイズ、Exchange 設定の指定、アカウントの追加、アカウントの削除、設定のエクスポート、および Send\Receive グループの指定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="aa3ae-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="aa3ae-120">OCT の詳細については、「OCT を使用してユーザー設定を[カスタマイズする」をOffice 2013。](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))</span><span class="sxs-lookup"><span data-stu-id="aa3ae-120">For information about the OCT, see [Use the OCT to customize Office 2013](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="aa3ae-121">この情報は、以降のバージョンにも適用Office。</span><span class="sxs-lookup"><span data-stu-id="aa3ae-121">Note that this information also applies to later versions of Office.</span></span>
