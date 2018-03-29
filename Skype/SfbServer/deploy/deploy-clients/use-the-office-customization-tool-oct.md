---
title: Skype for Business Server 2015 で Office カスタマイズ ツール (OCT) を使用する
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: '概要: Skype で、Office カスタマイズ ツールを使用して、クライアントのビジネスの方法です。'
ms.openlocfilehash: b0e8dd399af7a75a6f575d554cbe6c25c4e8ffd3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server-2015"></a><span data-ttu-id="c6fef-103">Skype for Business Server 2015 で Office カスタマイズ ツール (OCT) を使用する</span><span class="sxs-lookup"><span data-stu-id="c6fef-103">Use the Office Customization Tool (OCT) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c6fef-104">**の概要:**ビジネス クライアントに、Skype で、Office カスタマイズ ツールを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="c6fef-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="c6fef-105">Office カスタマイズ ツール (OCT) はセットアップ プログラムの一部であり、多くのカスタマイズにおける推奨ツールになっています。</span><span class="sxs-lookup"><span data-stu-id="c6fef-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="c6fef-106">OCT を使用して Office をカスタマイズし、カスタマイズ内容をセットアップ カスタマイズ (.msp) ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="c6fef-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="c6fef-107">そのファイルをネットワーク インストール ポイントの Updates フォルダーに配置します。</span><span class="sxs-lookup"><span data-stu-id="c6fef-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="c6fef-108">Office をインストールするときに、セットアップは Updates フォルダーのセットアップ カスタマイズ ファイルを検索し、カスタマイズ内容を適用します。</span><span class="sxs-lookup"><span data-stu-id="c6fef-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="c6fef-109">Updates フォルダーは、Office の初回インストール時にソフトウェア更新プログラムの展開にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6fef-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="c6fef-110">OCT は、セットアップの一部とは、ボリューム ライセンスを購入のバージョンの製品にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="c6fef-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="c6fef-111">入力して OCT を実行する`setup.exe /admin`、Office を含むネットワーク インストール ポイントのルートからコマンド ・ ラインでは、ソース ファイルです。</span><span class="sxs-lookup"><span data-stu-id="c6fef-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="c6fef-112">たとえば、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6fef-112">For example, use the following:</span></span>
  
 `\\server\share\Office15\setup.exe /admin`
  
<span data-ttu-id="c6fef-113">管理者は、OCT を使用してセットアップ カスタマイズ .msp ファイルを作成し、次の領域をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="c6fef-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="c6fef-114">**セットアップ**レベルは、以前、時に実行するカスタム プログラムを削除する Office のバージョンを表示するクライアントと既定の組織名、追加のネットワーク インストール ソース、プロダクト キー、使用許諾契約書の既定のインストール場所を指定するために使用、インストール、セキュリティ設定、およびセットアップ プロパティです。</span><span class="sxs-lookup"><span data-stu-id="c6fef-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="c6fef-115">**機能**ユーザー設定を構成して、Office 機能のインストール方法をカスタマイズするのにを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6fef-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="c6fef-116">管理者は、OCT を使用してユーザーの Office アプリケーションの設定の既定の初期値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6fef-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="c6fef-117">ユーザーは、インストール後、ほとんどの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c6fef-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="c6fef-118">**その他のコンテンツ**追加またはファイルを削除するために使用とを追加またはレジストリ エントリを削除し、ショートカットを構成します。</span><span class="sxs-lookup"><span data-stu-id="c6fef-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="c6fef-119">**Outlook**使用すると、ユーザーの既定の Outlook プロファイルをカスタマイズするのには、Exchange 設定の指定、アカウントを追加、アカウントを削除しての設定をエクスポートおよび送受信グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="c6fef-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="c6fef-120">OCT の詳細についてを参照してください[OCT を使用して Office 2013 をカスタマイズするのには](https://technet.microsoft.com/library/cc179132.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="c6fef-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://technet.microsoft.com/library/cc179132.aspx).</span></span> <span data-ttu-id="c6fef-121">この情報が Office 2016 にも適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c6fef-121">Note that this information also applies to Office 2016.</span></span>
  

