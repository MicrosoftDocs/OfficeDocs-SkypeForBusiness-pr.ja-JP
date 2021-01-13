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
description: '概要: Skype for Business クライアントで Office カスタマイズ ツールを使用する方法について説明します。'
ms.openlocfilehash: ba99f0556f3fb1d0e0f6870d1eaa7a3d2108b4d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812567"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="5ea45-103">Skype for Business Server Officeカスタマイズ ツール (OCT) を使用する</span><span class="sxs-lookup"><span data-stu-id="5ea45-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="5ea45-104">**概要:** Skype for Business クライアントで Office カスタマイズ ツールを使用する方法。</span><span class="sxs-lookup"><span data-stu-id="5ea45-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="5ea45-105">Office ツール (OCT) はセットアップ プログラムの一部であり、多くのカスタマイズに推奨されるツールです。</span><span class="sxs-lookup"><span data-stu-id="5ea45-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="5ea45-106">OCT を使用して、カスタマイズOfficeセットアップ カスタマイズ .msp ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="5ea45-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="5ea45-107">ネットワーク インストール ポイントの Updates フォルダーにファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="5ea45-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="5ea45-108">このファイルをOfficeセットアップは Updates フォルダーでセットアップ カスタマイズ ファイルを検索し、カスタマイズを適用します。</span><span class="sxs-lookup"><span data-stu-id="5ea45-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="5ea45-109">Updates フォルダーは、更新プログラムの初期インストール時にソフトウェア更新プログラムを展開する場合にのみOffice。</span><span class="sxs-lookup"><span data-stu-id="5ea45-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="5ea45-110">OCT はセットアップの一部であり、ボリューム ライセンスバージョンの製品にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="5ea45-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="5ea45-111">OCT を実行するには、ソース ファイルに含まれるネットワーク インストール ポイントのルートからコマンド ラインOffice  `setup.exe /admin` 入力します。</span><span class="sxs-lookup"><span data-stu-id="5ea45-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="5ea45-112">たとえば、次の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="5ea45-112">For example, use the following:</span></span>
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="5ea45-113">管理者は OCT を使用してセットアップ カスタマイズ .msp ファイルを作成し、次の領域をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="5ea45-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="5ea45-114">**セットアップ** クライアントの既定のインストール場所と既定の組織名、追加のネットワーク インストール ソース、プロダクト キー、エンドユーザー 使用許諾契約書、表示レベル、削除する以前のバージョンの Office、インストール中に実行するカスタム プログラム、セキュリティ設定、およびセットアップ プロパティを指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5ea45-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="5ea45-115">**機能** ユーザー設定を構成し、機能のインストールOfficeカスタマイズするために使用します。</span><span class="sxs-lookup"><span data-stu-id="5ea45-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="5ea45-116">管理者は OCT を使用して、ユーザーのアプリケーション設定にOffice既定値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5ea45-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="5ea45-117">ユーザーはインストール後に大部分の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="5ea45-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="5ea45-118">**その他のコンテンツ** ファイルの追加または削除、レジストリ エントリの追加または削除、およびショートカットの構成に使用します。</span><span class="sxs-lookup"><span data-stu-id="5ea45-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="5ea45-119">**Outlook** ユーザーの既定の Outlook プロファイルのカスタマイズ、Exchange 設定の指定、アカウントの追加、アカウントの削除と設定のエクスポート、および送受信グループの指定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5ea45-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="5ea45-120">OCT の詳細については、「OCT を使用してユーザー設定をカスタマイズ[する」をOffice 2013。](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))</span><span class="sxs-lookup"><span data-stu-id="5ea45-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="5ea45-121">この情報は、新しいバージョンのファイルにも適用Office。</span><span class="sxs-lookup"><span data-stu-id="5ea45-121">Note that this information also applies to later versions of Office.</span></span>
  

