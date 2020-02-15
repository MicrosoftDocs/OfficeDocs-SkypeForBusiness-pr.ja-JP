---
title: 'Lync Server 2013: Lync VDI プラグインのトラブルシューティング'
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
ms.openlocfilehash: f1d75e0801ec16957083f2e9fef043080c771ea9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="4dc22-102">Lync Server 2013 での Lync VDI プラグインのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4dc22-102">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dc22-103">_**トピックの最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="4dc22-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a><span data-ttu-id="4dc22-104">Lync VDI プラグインをシンクライアントにインストールする際の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4dc22-104">Troubleshooting Issues with Installing the Lync VDI Plug-in on a Thin Client</span></span>

<span data-ttu-id="4dc22-105">シン クライアントへの VDI プラグインのインストールに関して問題がある場合は、次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4dc22-105">If there are issues with installing the VDI plug-in on a thin client, check the following:</span></span>

  - <span data-ttu-id="4dc22-106">TEMP および TMP システム変数で指定したフォルダーに十分な容量がある。</span><span class="sxs-lookup"><span data-stu-id="4dc22-106">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>

  - <span data-ttu-id="4dc22-p101">書き込み保護がオフになっている。手順については、デバイス メーカーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dc22-p101">Ensure that write-protect is turned off. Refer to your device manufacturer’s documentation for instructions.</span></span>

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="4dc22-109">ペアリングに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4dc22-109">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="4dc22-110">VDI プラグインのペアリングに失敗すると、右下のペアリング アイコンが赤色の "X" で表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dc22-110">When VDI plug-in pairing fails, the pairing icon in the lower right displays as a red “X” as shown:</span></span>

<span data-ttu-id="4dc22-111">![ペアリングが成功したことを示す Lync VDI アイコン](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "ペアリングが成功したことを示す Lync VDI アイコン")</span><span class="sxs-lookup"><span data-stu-id="4dc22-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>

<span data-ttu-id="4dc22-112">失敗の原因の可能性と対策を、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="4dc22-112">The following are possible reasons for failures and the corrective actions you can take.</span></span>

  - <span data-ttu-id="4dc22-113">**ユーザーがサインインの際に入力した資格情報が正しくない。**</span><span class="sxs-lookup"><span data-stu-id="4dc22-113">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="4dc22-114">ユーザーは、Lync からサインアウトし、正しい資格情報を使用して再度サインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dc22-114">The user should sign out of Lync and sign in again with the correct credentials.</span></span> <span data-ttu-id="4dc22-115">ペアリングのダイアログ ボックスが再表示され、ペアリングに成功したかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dc22-115">The pairing dialog box will reappear and show whether pairing is successful.</span></span>

  - <span data-ttu-id="4dc22-116">**リモート デスクトップ クライアントの別のインスタンスが実行している。**</span><span class="sxs-lookup"><span data-stu-id="4dc22-116">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="4dc22-117">Windows でリモートデスクトップ接続を使用している場合、ユーザーは次の操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dc22-117">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
    1.  <span data-ttu-id="4dc22-118">タスク マネージャーを起動します。**Alt+Ctrl+Del** キーを押し、[**タスク マネージャーの起動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dc22-118">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
    2.  <span data-ttu-id="4dc22-119">[**プロセス**] タブをクリックし、リスト内で **mstsc.exe** という名前のすべてのプロセスを見つけます。</span><span class="sxs-lookup"><span data-stu-id="4dc22-119">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
    3.  <span data-ttu-id="4dc22-120">各 **mstsc.exe** プロセスを強調表示し、[**プロセスの終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dc22-120">Highlight each **mstsc.exe** process and then click **End Process**.</span></span>
    
    4.  <span data-ttu-id="4dc22-121">新しいリモート デスクトップ セッションを起動して、再び接続を試みます。</span><span class="sxs-lookup"><span data-stu-id="4dc22-121">Start a new remote desktop session and try connecting again.</span></span>

  - <span data-ttu-id="4dc22-122">**必要なファイルが適切にインストールされていない。**</span><span class="sxs-lookup"><span data-stu-id="4dc22-122">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="4dc22-123">プラグインがローカルコンピューターにインストールされた後、C:\\Program Files\\Microsoft Office\\Office15 (または適切なドライブ文字) の下に次のファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dc22-123">After the plug-in is installed on the local computer, the following files should be present under C:\\Program Files\\Microsoft Office\\Office15 (or the appropriate drive letter):</span></span>
    
      - <span data-ttu-id="4dc22-124">LyncVdiPlugin</span><span class="sxs-lookup"><span data-stu-id="4dc22-124">LyncVdiPlugin.dll</span></span>
    
      - <span data-ttu-id="4dc22-125">UcVdi .dll</span><span class="sxs-lookup"><span data-stu-id="4dc22-125">UcVdi.dll</span></span>
    
    <span data-ttu-id="4dc22-126">VDI ペアリングに何か問題がある場合は、これらのファイルがローカル コンピューター上に存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4dc22-126">If there are any issues with VDI pairing, check to make sure that these files are present on the local computer.</span></span>

  - <span data-ttu-id="4dc22-127">**Lync クライアントは、ローカルコンピューター上で実行されています。**</span><span class="sxs-lookup"><span data-stu-id="4dc22-127">**The Lync client is running on the local computer.**</span></span>
    
    <span data-ttu-id="4dc22-128">Lync VDI プラグインを使用するには、Lync クライアントがローカルコンピューター上で実行されていてはなりません。そうでないと、ペアリングは失敗します。</span><span class="sxs-lookup"><span data-stu-id="4dc22-128">To use the Lync VDI plugin, a Lync client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="4dc22-129">ベストプラクティスとして、ユーザーは、Lync クライアントをローカルコンピューターにインストールしないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="4dc22-129">As a best practice, the user should not install a Lync client on the local computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

