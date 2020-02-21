---
title: 'Lync Server 2013: Office カスタマイズツール (OCT) の使用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c55cfa8fd795feeca5e265f43823c4263512211f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a><span data-ttu-id="85d01-102">Lync Server 2013 で Office カスタマイズツール (OCT) を使用する</span><span class="sxs-lookup"><span data-stu-id="85d01-102">Using the Office Customization Tool (OCT) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85d01-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="85d01-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="85d01-104">Office カスタマイズツール (OCT) はセットアッププログラムの一部であり、多くのカスタマイズに推奨されるツールです。</span><span class="sxs-lookup"><span data-stu-id="85d01-104">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="85d01-105">OCT を使用して、Office をカスタマイズし、カスタマイズをセットアップカスタマイズ .msp ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="85d01-105">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="85d01-106">このファイルは、ネットワークインストールポイントの Updates フォルダーに配置します。</span><span class="sxs-lookup"><span data-stu-id="85d01-106">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="85d01-107">Office をインストールすると、セットアッププログラムによって Updates フォルダーのセットアップカスタマイズファイルが検索され、カスタマイズが適用されます。</span><span class="sxs-lookup"><span data-stu-id="85d01-107">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="85d01-108">Updates フォルダーは、Office 2013 の初期インストール時にソフトウェア更新プログラムを展開する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="85d01-108">The Updates folder can be used only to deploy software updates during an initial installation of Office 2013.</span></span>

<span data-ttu-id="85d01-109">OCT はセットアップの一部であり、ボリュームライセンスバージョンの製品に含まれています。</span><span class="sxs-lookup"><span data-stu-id="85d01-109">The OCT is part of setup and it is included in volume license versions of the product.</span></span> <span data-ttu-id="85d01-110">OCT を実行するには`setup.exe /admin` 、Office 2013 ソースファイルが含まれているネットワークインストールポイントのルートからコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="85d01-110">You run the OCT by typing `setup.exe /admin` at the command line from the root of the network installation point that contains the Office 2013 source files.</span></span> <span data-ttu-id="85d01-111">たとえば、次の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="85d01-111">For example, use the following:</span></span>

`\\server\share\Office15\setup.exe /admin`

<span data-ttu-id="85d01-112">管理者は OCT を使用して、セットアップカスタマイズ .msp ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="85d01-112">Administrators use the OCT to create a setup customization .msp file.</span></span> <span data-ttu-id="85d01-113">Microsoft Office 2010 OCT と同様に、管理者は次の領域をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="85d01-113">As in the Microsoft Office 2010 OCT, administrators can customize the following areas:</span></span>

  - <span data-ttu-id="85d01-114">**セットアップ**クライアントと既定の組織名の既定のインストール場所、追加のネットワークインストールソース、プロダクトキー、使用許諾契約書、表示レベル、削除する Office の以前のバージョン、インストール時に実行するカスタムプログラム、セキュリティ設定、およびセットアップのプロパティを指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="85d01-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>

  - <span data-ttu-id="85d01-115">**機能**ユーザー設定を構成し、Office 機能のインストール方法をカスタマイズするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="85d01-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="85d01-116">管理者は、OCT を使用して、ユーザーの Office アプリケーション設定の初期既定値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="85d01-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="85d01-117">ユーザーはインストール後に大部分の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="85d01-117">Users can modify most of the settings after the installation.</span></span>

  - <span data-ttu-id="85d01-118">**その他のコンテンツ**ファイルを追加または削除したり、レジストリエントリを追加または削除したり、ショートカットを構成したりするために使用します。</span><span class="sxs-lookup"><span data-stu-id="85d01-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>

  - <span data-ttu-id="85d01-119">**Outlook**ユーザーの既定の Outlook プロファイルのカスタマイズ、Exchange の設定の指定、アカウントの追加、アカウントの削除と設定のエクスポート\\、および送信受信グループの指定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="85d01-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\\Receive groups.</span></span>

<span data-ttu-id="85d01-120">OCT の詳細については<https://go.microsoft.com/fwlink/p/?linkid=267516>、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85d01-120">For information about the OCT, see <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

