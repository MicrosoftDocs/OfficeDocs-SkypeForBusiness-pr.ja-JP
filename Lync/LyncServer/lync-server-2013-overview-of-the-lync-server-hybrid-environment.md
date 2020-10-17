---
title: 'Lync Server 2013: Lync Server ハイブリッド環境の概要'
description: 'Lync Server 2013: Lync Server ハイブリッド環境の概要。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95b0ae433dafad349d7ef9b6328e43dbc308579c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552393"
---
# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a><span data-ttu-id="6bd2f-103">Lync Server 2013 ハイブリッド環境の概要</span><span class="sxs-lookup"><span data-stu-id="6bd2f-103">Overview of the Lync Server 2013 hybrid environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bd2f-104">_**トピックの最終更新日:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="6bd2f-104">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="6bd2f-105">Lync Server 2013 ハイブリッド環境とは、オンプレミスの Lync Server 2013 に所属するユーザーや、Lync Online に所属している他のユーザーが、user@contoso.com などの同じドメインを共有する展開のことを指します。</span><span class="sxs-lookup"><span data-stu-id="6bd2f-105">Lync Server 2013 hybrid environment refers to a deployment in which there are some users homed to the on-premises Lync Server 2013 and other users homed to Lync Online, but users share the same domain, such as user@contoso.com.</span></span>

<div>

## <a name="about-this-guide"></a><span data-ttu-id="6bd2f-106">このガイドについて</span><span class="sxs-lookup"><span data-stu-id="6bd2f-106">About this Guide</span></span>

<span data-ttu-id="6bd2f-107">このガイドでは、lync Online との相互運用性を実現するために Lync Server 2013 環境を構成し、オンプレミス展開から Lync Online を使用するようにユーザーを移動するために必要なタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6bd2f-107">This guide describes the tasks necessary to configure your Lync Server 2013 environment for interoperability with Lync Online, and then to move users from your on-premises deployment to use Lync Online.</span></span>

</div>

<div>

## <a name="prerequisites"></a><span data-ttu-id="6bd2f-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="6bd2f-108">Prerequisites</span></span>

<span data-ttu-id="6bd2f-109">ハイブリッド展開を構成するためのタスクを完了するには、次のアプリケーションとユーティリティがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bd2f-109">You will need to have the following applications and utilities installed to complete the tasks for configuring a deployment for hybrid.</span></span> <span data-ttu-id="6bd2f-110">これらのファイルのインストーラーは、展開で提供されるインストールメディアと、次の一覧に含まれているリンクに含まれています。</span><span class="sxs-lookup"><span data-stu-id="6bd2f-110">The installers for these files are included on the installation media provided for your deployment, as well as at the links included in the following list.</span></span>

  - [<span data-ttu-id="6bd2f-111">Active Directory フェデレーション サービス (AD FS) 2.0</span><span class="sxs-lookup"><span data-stu-id="6bd2f-111">Active Directory Federation Services (AD FS) 2.0</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257305)

  - [<span data-ttu-id="6bd2f-112">Microsoft ディレクトリ同期ツール9.1</span><span class="sxs-lookup"><span data-stu-id="6bd2f-112">Microsoft Directory Synchronization Tool 9.1</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257307)

  - [<span data-ttu-id="6bd2f-113">AD FS を使用したシングルサインオン用の Windows PowerShell のインストール</span><span class="sxs-lookup"><span data-stu-id="6bd2f-113">Install Windows PowerShell for single sign-on with AD FS</span></span>](https://go.microsoft.com/fwlink/p/?linkid=398710)

  - <span data-ttu-id="6bd2f-114">Microsoft Online Services サインインアシスタント (msoidcli-7.0.msi) は、microsoft 365 のデスクトップセットアップに含まれています。これは、Microsoft 365 管理センターからリンクされているダウンロードページから入手できます。</span><span class="sxs-lookup"><span data-stu-id="6bd2f-114">Microsoft Online Services Sign-in Assistant (msoidcli-7.0.msi) is included with the Desktop Setup for Microsoft 365, which can be obtained from the Downloads page linked to from the Microsoft 365 admin center.</span></span>

</div>

<div>

## <a name="administrator-credentials"></a><span data-ttu-id="6bd2f-115">管理者の資格情報</span><span class="sxs-lookup"><span data-stu-id="6bd2f-115">Administrator Credentials</span></span>

<span data-ttu-id="6bd2f-116">管理者の資格情報を入力するように求めるメッセージが表示されたら、Microsoft 365 または Office 365 組織の管理者アカウントのユーザー名とパスワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="6bd2f-116">When you are asked to provide your administrator credentials, use the username and password for the administrator account for your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="6bd2f-117">Active Directory フェデレーションサービス (AD FS) 2.0、ディレクトリ同期、シングルサインオン、フェデレーション、および Lync Online へのユーザーの移動を構成するときに、これらの資格情報を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6bd2f-117">You will also use these credentials when you configure Active Directory Federation Services (AD FS) 2.0, Directory Synchronization, Single sign-on, federation, and moving users to Lync Online.</span></span>

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a><span data-ttu-id="6bd2f-118">Lync Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="6bd2f-118">Connecting to Lync Online PowerShell</span></span>

<span data-ttu-id="6bd2f-119">管理者は、Windows PowerShell を使用して Lync Online と Lync Online ユーザーアカウントを管理できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6bd2f-119">Administrators now have the ability to use Windows PowerShell to manage Lync Online and their Lync Online user accounts.</span></span> <span data-ttu-id="6bd2f-120">これを行うには、まず、Microsoft ダウンロードセンター (から Lync Online Connector モジュールをダウンロードしてインストールする必要があり https://go.microsoft.com/fwlink/?LinkId=294688) ます。</span><span class="sxs-lookup"><span data-stu-id="6bd2f-120">To do this, you must first download and install the Lync Online Connector Module from the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="6bd2f-121">Lync Online コネクタモジュールをダウンロード、インストール、および使用する方法、および Windows PowerShell を使用して Lync Online を管理する方法の詳細については、「 [Windows powershell を使用して Lync online を管理する](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bd2f-121">For more information on downloading, installing, and using the Lync Online Connector Module, and for detailed information on using Windows PowerShell to manage Lync Online, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

