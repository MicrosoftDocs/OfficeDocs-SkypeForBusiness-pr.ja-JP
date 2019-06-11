---
title: 'Lync Server 2013: Lync Server のハイブリッド環境の概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0420e4aaded9f5ae90d26c4cbdc176e7fb4c6bb5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a><span data-ttu-id="15fc7-102">Lync Server 2013 ハイブリッド環境の概要</span><span class="sxs-lookup"><span data-stu-id="15fc7-102">Overview of the Lync Server 2013 hybrid environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15fc7-103">_**最終更新日:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="15fc7-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="15fc7-104">Lync Server 2013 ハイブリッド環境とは、オンプレミスの Lync Server 2013 およびその他のユーザーが Lync Online に接続しているが、ユーザーが user@contoso.com などの同じドメインを共有している展開を指します。</span><span class="sxs-lookup"><span data-stu-id="15fc7-104">Lync Server 2013 hybrid environment refers to a deployment in which there are some users homed to the on-premises Lync Server 2013 and other users homed to Lync Online, but users share the same domain, such as user@contoso.com.</span></span>

<div>

## <a name="about-this-guide"></a><span data-ttu-id="15fc7-105">このガイドについて</span><span class="sxs-lookup"><span data-stu-id="15fc7-105">About this Guide</span></span>

<span data-ttu-id="15fc7-106">このガイドでは、lync Online との相互運用性を確保するために Lync Server 2013 環境を構成するために必要なタスクについて説明し、ユーザーをオンプレミスの展開から Lync Online を使用するように移動するために必要な作業について説明します</span><span class="sxs-lookup"><span data-stu-id="15fc7-106">This guide describes the tasks necessary to configure your Lync Server 2013 environment for interoperability with Lync Online, and then to move users from your on-premises deployment to use Lync Online.</span></span>

</div>

<div>

## <a name="prerequisites"></a><span data-ttu-id="15fc7-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="15fc7-107">Prerequisites</span></span>

<span data-ttu-id="15fc7-108">ハイブリッド展開を構成するためのタスクを実行するには、次のアプリケーションとユーティリティがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="15fc7-108">You will need to have the following applications and utilities installed to complete the tasks for configuring a deployment for hybrid.</span></span> <span data-ttu-id="15fc7-109">これらのファイルのインストーラーは、展開用に提供されているインストールメディアと、次の一覧に記載されているリンクに含まれています。</span><span class="sxs-lookup"><span data-stu-id="15fc7-109">The installers for these files are included on the installation media provided for your deployment, as well as at the links included in the following list.</span></span>

  - [<span data-ttu-id="15fc7-110">Active Directory フェデレーションサービス (AD FS) 2.0</span><span class="sxs-lookup"><span data-stu-id="15fc7-110">Active Directory Federation Services (AD FS) 2.0</span></span>](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [<span data-ttu-id="15fc7-111">Microsoft ディレクトリ同期ツール9.1</span><span class="sxs-lookup"><span data-stu-id="15fc7-111">Microsoft Directory Synchronization Tool 9.1</span></span>](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [<span data-ttu-id="15fc7-112">AD FS を使ってシングルサインオン用に Windows PowerShell をインストールする</span><span class="sxs-lookup"><span data-stu-id="15fc7-112">Install Windows PowerShell for single sign-on with AD FS</span></span>](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - <span data-ttu-id="15fc7-113">Microsoft Online Services サインインアシスタント (msoidcli-) は、office 365 のデスクトップセットアップに含まれています。 office 365 管理ポータルからリンクされたダウンロードページから入手できます。</span><span class="sxs-lookup"><span data-stu-id="15fc7-113">Microsoft Online Services Sign-in Assistant (msoidcli-7.0.msi) is included with the Desktop Setup for Office 365, which can be obtained from the Downloads page linked to from the Office 365 Admin portal.</span></span>

</div>

<div>

## <a name="administrator-credentials"></a><span data-ttu-id="15fc7-114">管理者の資格情報</span><span class="sxs-lookup"><span data-stu-id="15fc7-114">Administrator Credentials</span></span>

<span data-ttu-id="15fc7-115">管理者の資格情報を入力するように求められたら、Office 365 テナントの管理者アカウントのユーザー名とパスワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="15fc7-115">When you are asked to provide your administrator credentials, use the username and password for the administrator account for your Office 365 tenant.</span></span> <span data-ttu-id="15fc7-116">Active Directory フェデレーションサービス (AD FS) の2.0、ディレクトリ同期、シングルサインオン、フェデレーション、ユーザーの Lync Online への移動を構成するときにも、これらの資格情報を使います。</span><span class="sxs-lookup"><span data-stu-id="15fc7-116">You will also use these credentials when you configure Active Directory Federation Services (AD FS) 2.0, Directory Synchronization, Single sign-on, federation, and moving users to Lync Online.</span></span>

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a><span data-ttu-id="15fc7-117">Lync Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="15fc7-117">Connecting to Lync Online PowerShell</span></span>

<span data-ttu-id="15fc7-118">管理者は、Windows PowerShell を使用して Lync Online と Lync Online のユーザーアカウントを管理することができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="15fc7-118">Administrators now have the ability to use Windows PowerShell to manage Lync Online and their Lync Online user accounts.</span></span> <span data-ttu-id="15fc7-119">そのためには、まず Microsoft ダウンロードセンター (http://go.microsoft.com/fwlink/?LinkId=294688)) から Lync Online Connector モジュールをダウンロードしてインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="15fc7-119">To do this, you must first download and install the Lync Online Connector Module from the Microsoft Download Center (http://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="15fc7-120">Lync Online Connector モジュールのダウンロード、インストール、および使用の詳細と Windows PowerShell を使用して Lync Online を管理する方法の詳細については、「 [Windows Powershell を使用して Lync online を管理する](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15fc7-120">For more information on downloading, installing, and using the Lync Online Connector Module, and for detailed information on using Windows PowerShell to manage Lync Online, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

