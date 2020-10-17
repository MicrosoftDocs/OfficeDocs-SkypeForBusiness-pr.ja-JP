---
title: 'Lync Server 2013: Lync VDI プラグインのトラブルシューティング'
description: 'Lync Server 2013: Lync VDI プラグインのトラブルシューティング。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cd2c0e3c8a47225f00ce280706dea2287e4dc8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548943"
---
# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="6596f-103">Lync Server 2013 での Lync VDI プラグインのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6596f-103">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6596f-104">_**トピックの最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="6596f-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a><span data-ttu-id="6596f-105">Lync VDI プラグインをシンクライアントにインストールする際の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6596f-105">Troubleshooting Issues with Installing the Lync VDI Plug-in on a Thin Client</span></span>

<span data-ttu-id="6596f-106">シン クライアントへの VDI プラグインのインストールに関して問題がある場合は、次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6596f-106">If there are issues with installing the VDI plug-in on a thin client, check the following:</span></span>

  - <span data-ttu-id="6596f-107">TEMP および TMP システム変数で指定したフォルダーに十分な容量がある。</span><span class="sxs-lookup"><span data-stu-id="6596f-107">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>

  - <span data-ttu-id="6596f-p101">書き込み保護がオフになっている。手順については、デバイス メーカーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6596f-p101">Ensure that write-protect is turned off. Refer to your device manufacturer’s documentation for instructions.</span></span>

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="6596f-110">ペアリングに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6596f-110">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="6596f-111">VDI プラグインのペアリングに失敗すると、右下のペアリング アイコンが赤色の "X" で表示されます。</span><span class="sxs-lookup"><span data-stu-id="6596f-111">When VDI plug-in pairing fails, the pairing icon in the lower right displays as a red “X” as shown:</span></span>

<span data-ttu-id="6596f-112">![ペアリングが成功したことを示す Lync VDI アイコン](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "ペアリングが成功したことを示す Lync VDI アイコン")</span><span class="sxs-lookup"><span data-stu-id="6596f-112">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>

<span data-ttu-id="6596f-113">失敗の原因の可能性と対策を、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="6596f-113">The following are possible reasons for failures and the corrective actions you can take.</span></span>

  - <span data-ttu-id="6596f-114">**ユーザーがサインインの際に入力した資格情報が正しくない。**</span><span class="sxs-lookup"><span data-stu-id="6596f-114">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="6596f-115">ユーザーは、Lync からサインアウトし、正しい資格情報を使用して再度サインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6596f-115">The user should sign out of Lync and sign in again with the correct credentials.</span></span> <span data-ttu-id="6596f-116">ペアリングのダイアログ ボックスが再表示され、ペアリングに成功したかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6596f-116">The pairing dialog box will reappear and show whether pairing is successful.</span></span>

  - <span data-ttu-id="6596f-117">**リモート デスクトップ クライアントの別のインスタンスが実行している。**</span><span class="sxs-lookup"><span data-stu-id="6596f-117">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="6596f-118">Windows でリモートデスクトップ接続を使用している場合、ユーザーは次の操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6596f-118">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
    1.  <span data-ttu-id="6596f-119">タスク マネージャーを起動します。**Alt+Ctrl+Del** キーを押し、[**タスク マネージャーの起動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6596f-119">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
    2.  <span data-ttu-id="6596f-120">[**プロセス**] タブをクリックし、リスト内で **mstsc.exe** という名前のすべてのプロセスを見つけます。</span><span class="sxs-lookup"><span data-stu-id="6596f-120">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
    3.  <span data-ttu-id="6596f-121">各 **mstsc.exe** プロセスを強調表示し、[**プロセスの終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6596f-121">Highlight each **mstsc.exe** process and then click **End Process**.</span></span>
    
    4.  <span data-ttu-id="6596f-122">新しいリモート デスクトップ セッションを起動して、再び接続を試みます。</span><span class="sxs-lookup"><span data-stu-id="6596f-122">Start a new remote desktop session and try connecting again.</span></span>

  - <span data-ttu-id="6596f-123">**必要なファイルが適切にインストールされていない。**</span><span class="sxs-lookup"><span data-stu-id="6596f-123">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="6596f-124">プラグインがローカルコンピューターにインストールされた後、C: \\ Program files \\ Microsoft Office \\ Office15 (または適切なドライブ文字) の下に次のファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6596f-124">After the plug-in is installed on the local computer, the following files should be present under C:\\Program Files\\Microsoft Office\\Office15 (or the appropriate drive letter):</span></span>
    
      - <span data-ttu-id="6596f-125">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="6596f-125">LyncVdiPlugin.dll</span></span>
    
      - <span data-ttu-id="6596f-126">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="6596f-126">UcVdi.dll</span></span>
    
    <span data-ttu-id="6596f-127">VDI ペアリングに何か問題がある場合は、これらのファイルがローカル コンピューター上に存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6596f-127">If there are any issues with VDI pairing, check to make sure that these files are present on the local computer.</span></span>

  - <span data-ttu-id="6596f-128">**Lync クライアントは、ローカルコンピューター上で実行されています。**</span><span class="sxs-lookup"><span data-stu-id="6596f-128">**The Lync client is running on the local computer.**</span></span>
    
    <span data-ttu-id="6596f-129">Lync VDI プラグインを使用するには、Lync クライアントがローカルコンピューター上で実行されていてはなりません。そうでないと、ペアリングは失敗します。</span><span class="sxs-lookup"><span data-stu-id="6596f-129">To use the Lync VDI plugin, a Lync client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="6596f-130">ベストプラクティスとして、ユーザーは、Lync クライアントをローカルコンピューターにインストールしないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="6596f-130">As a best practice, the user should not install a Lync client on the local computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

