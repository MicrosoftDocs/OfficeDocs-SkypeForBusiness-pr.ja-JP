---
title: 'Lync Server 2013: Lync VDI プラグインのトラブルシューティング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7afaa0067e4ca06f8bb40ff201b090a45c66f442
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="e9115-102">Lync Server 2013 での Lync VDI プラグインのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e9115-102">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9115-103">_**最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="e9115-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a><span data-ttu-id="e9115-104">Thin クライアントに Lync VDI プラグインをインストールする際の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e9115-104">Troubleshooting Issues with Installing the Lync VDI Plug-in on a Thin Client</span></span>

<span data-ttu-id="e9115-105">シンクライアントに VDI プラグインをインストールするときに問題が発生した場合は、次の点を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e9115-105">If there are issues with installing the VDI plug-in on a thin client, check the following:</span></span>

  - <span data-ttu-id="e9115-106">TEMP および TMP システム変数で指定したフォルダーに十分な容量がある。</span><span class="sxs-lookup"><span data-stu-id="e9115-106">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>

  - <span data-ttu-id="e9115-p101">書き込み保護がオフになっている。手順については、デバイス メーカーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9115-p101">Ensure that write-protect is turned off. Refer to your device manufacturer’s documentation for instructions.</span></span>

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="e9115-109">ペアリングに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e9115-109">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="e9115-110">VDI プラグインのペアリングに失敗した場合、右下のペアリングアイコンは、次のように赤い "X" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9115-110">When VDI plug-in pairing fails, the pairing icon in the lower right displays as a red “X” as shown:</span></span>

<span data-ttu-id="e9115-111">![成功したペアリングを示す LYNC VDI アイコン](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "成功したペアリングを示す LYNC VDI アイコン")</span><span class="sxs-lookup"><span data-stu-id="e9115-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>

<span data-ttu-id="e9115-112">次のような原因が考えられます。問題が発生した場合は、次のことを行ってください。</span><span class="sxs-lookup"><span data-stu-id="e9115-112">The following are possible reasons for failures and the corrective actions you can take.</span></span>

  - <span data-ttu-id="e9115-113">**ユーザーがサインインの際に入力した資格情報が正しくない。**</span><span class="sxs-lookup"><span data-stu-id="e9115-113">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="e9115-114">ユーザーは、Lync からサインアウトし、正しい資格情報を使用してもう一度サインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9115-114">The user should sign out of Lync and sign in again with the correct credentials.</span></span> <span data-ttu-id="e9115-115">ペアリングのダイアログ ボックスが再表示され、ペアリングに成功したかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9115-115">The pairing dialog box will reappear and show whether pairing is successful.</span></span>

  - <span data-ttu-id="e9115-116">**リモート デスクトップ クライアントの別のインスタンスが実行している。**</span><span class="sxs-lookup"><span data-stu-id="e9115-116">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="e9115-117">Windows でリモートデスクトップ接続を使用している場合、ユーザーは次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9115-117">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
    1.  <span data-ttu-id="e9115-118">タスク マネージャーを起動します。**Alt+Ctrl+Del** キーを押し、[**タスク マネージャーの起動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9115-118">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
    2.  <span data-ttu-id="e9115-119">[**プロセス**] タブをクリックし、リスト内で **mstsc.exe** という名前のすべてのプロセスを見つけます。</span><span class="sxs-lookup"><span data-stu-id="e9115-119">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
    3.  <span data-ttu-id="e9115-120">各 **mstsc.exe** プロセスを強調表示し、[**プロセスの終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9115-120">Highlight each **mstsc.exe** process and then click **End Process**.</span></span>
    
    4.  <span data-ttu-id="e9115-121">新しいリモート デスクトップ セッションを起動して、もう一度接続してみます。</span><span class="sxs-lookup"><span data-stu-id="e9115-121">Start a new remote desktop session and try connecting again.</span></span>

  - <span data-ttu-id="e9115-122">**必要なファイルが適切にインストールされていない。**</span><span class="sxs-lookup"><span data-stu-id="e9115-122">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="e9115-123">プラグインをローカルコンピューターにインストールした後、C:\\Program Files\\Microsoft Office\\Office15 (または適切なドライブ文字) の下に次のファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9115-123">After the plug-in is installed on the local computer, the following files should be present under C:\\Program Files\\Microsoft Office\\Office15 (or the appropriate drive letter):</span></span>
    
      - <span data-ttu-id="e9115-124">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="e9115-124">LyncVdiPlugin.dll</span></span>
    
      - <span data-ttu-id="e9115-125">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="e9115-125">UcVdi.dll</span></span>
    
    <span data-ttu-id="e9115-126">VDI ペアリングで問題が発生した場合は、これらのファイルがローカルコンピューターに存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e9115-126">If there are any issues with VDI pairing, check to make sure that these files are present on the local computer.</span></span>

  - <span data-ttu-id="e9115-127">**Lync クライアントがローカルコンピューターで実行されている。**</span><span class="sxs-lookup"><span data-stu-id="e9115-127">**The Lync client is running on the local computer.**</span></span>
    
    <span data-ttu-id="e9115-128">Lync VDI プラグインを使用するには、Lync クライアントがローカルコンピューターで実行されていない必要があります。そうでないと、ペアリングは失敗します。</span><span class="sxs-lookup"><span data-stu-id="e9115-128">To use the Lync VDI plugin, a Lync client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="e9115-129">ベストプラクティスとして、ユーザーはローカルコンピューターに Lync クライアントをインストールしないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9115-129">As a best practice, the user should not install a Lync client on the local computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

