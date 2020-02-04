---
title: 'Lync Server 2013: ベストプラクティスアナライザーの更新を確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking for updates to Best Practices Analyzer
ms:assetid: 06f1da8b-99a7-4871-911e-bfb7542baced
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204645(v=OCS.15)
ms:contentKeyID: 48183307
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffd05761a1c107ac72c7b9c3242fb18a5a3c7a27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-for-updates-to-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="18020-102">Lync Server 2013 でのベストプラクティスアナライザーの更新プログラムを確認する</span><span class="sxs-lookup"><span data-stu-id="18020-102">Checking for updates to Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18020-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="18020-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="18020-104">ベストプラクティスアナライザーを開始すると、ツールの最新の更新プログラムを検索するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="18020-104">When you start Best Practices Analyzer, the tool provides you with an option to search for the latest updates to the tool.</span></span> <span data-ttu-id="18020-105">更新プログラムが入手可能な場合は、更新プログラムをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="18020-105">If an update is available, you can download the update.</span></span> <span data-ttu-id="18020-106">更新プログラムをダウンロードしないようにした場合、またはベストプラクティスアナライザーがインターネットにアクセスできない場合は、コンピューターに既に存在するバージョンを引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="18020-106">If you choose not to download updates, or if Best Practices Analyzer cannot access the Internet, you can continue to use the version that is already on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18020-107">インターネットにアクセスするためにプロキシ認証が必要な場合は、ベストプラクティスアナライザーでダウンロードできる新しい更新プログラムにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="18020-107">If you need proxy authentication to access the Internet, Best Practices Analyzer cannot access new updates for you to download.</span></span> <span data-ttu-id="18020-108">ただし、Microsoft ダウンロードセンターから最新バージョンの RtcBPA .msi を手動でダウンロードすることができ<A href="http://go.microsoft.com/fwlink/p/?linkid=266539">http://go.microsoft.com/fwlink/p/?linkId=266539</A>ます。</span><span class="sxs-lookup"><span data-stu-id="18020-108">However, you can manually download the latest version of RtcBPA.msi from the Microsoft Download Center at <A href="http://go.microsoft.com/fwlink/p/?linkid=266539">http://go.microsoft.com/fwlink/p/?linkId=266539</A>.</span></span> <span data-ttu-id="18020-109">ファイルをダウンロードした後、ベストプラクティスアナライザーを更新するコンピューターにファイルをコピーし、.msi ファイルを使用してそのコンピューターに新しいバージョンのツールをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="18020-109">After downloading the file, you can copy it to the computer on which you want to update Best Practices Analyzer and use the .msi file to install the new version of the tool on that computer.</span></span>



</div>

<span data-ttu-id="18020-110">ベストプラクティスアナライザーの規則を更新するには、ローカルコンピューターの管理者としてツールを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18020-110">To update Best Practices Analyzer rules, you must run the tool as an Administrator on the local computer.</span></span> <span data-ttu-id="18020-111">管理者グループのメンバーであるアカウントを使用してログオンしておらず、更新が検出された場合は、ベストプラクティスアナライザーを終了して、次の手順に従ってプログラムを起動します。</span><span class="sxs-lookup"><span data-stu-id="18020-111">If you are not logged on using an account that is a member of the Administrators group and updates are detected, close Best Practices Analyzer, and then use the following procedure to start the program.</span></span>

<div>

## <a name="to-open-best-practices-analyzer-as-administrator-to-check-for-updates"></a><span data-ttu-id="18020-112">更新プログラムを確認するために、管理者としてベストプラクティスアナライザーを開くには</span><span class="sxs-lookup"><span data-stu-id="18020-112">To open Best Practices Analyzer as Administrator to check for updates</span></span>

1.  <span data-ttu-id="18020-113">ベストプラクティスアナライザーがインストールされているコンピューターで、[**スタート**] ボタンをクリックし、[ **Microsoft Lync Server 2013**] をポイントして、[**ベストプラクティスアナライザー**] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18020-113">On a computer on which Best Practices Analyzer is installed, click **Start**, point to **Microsoft Lync Server 2013**, right-click **Best Practices Analyzer**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="18020-114">管理者グループのメンバーであるアカウントの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="18020-114">Specify credentials of an account that is a member of the Administrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

