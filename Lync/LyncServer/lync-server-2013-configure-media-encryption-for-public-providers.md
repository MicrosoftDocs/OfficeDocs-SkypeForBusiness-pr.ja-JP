---
title: 'Lync Server 2013: パブリックプロバイダー用のメディアの暗号化の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73d914e77f5ae53e5b7e22cdc3392fe6bc22ef64
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="98eac-102">Lync Server 2013 のパブリックプロバイダーに対するメディアの暗号化の構成</span><span class="sxs-lookup"><span data-stu-id="98eac-102">Configure media encryption for public providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98eac-103">_**トピックの最終更新日:** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="98eac-103">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="98eac-104">Windows Live Messenger で音声ビデオ (A/V) フェデレーションを実装している場合は、Lync Server の暗号化レベルと EnablePublicCloudAccess ポリシーの2つのパラメーターを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98eac-104">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="98eac-105">既定では、暗号化レベルは「必須」です。</span><span class="sxs-lookup"><span data-stu-id="98eac-105">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="98eac-106">この設定を「サポート」に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98eac-106">You must change this setting to Supported.</span></span> <span data-ttu-id="98eac-107">EnablePublicCloudAccess ポリシーが false に設定されている場合は、**True** に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98eac-107">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="98eac-108">これは、Lync Server 管理シェルから実行できます。</span><span class="sxs-lookup"><span data-stu-id="98eac-108">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="98eac-109">Windows Live のフェデレーションを構成する</span><span class="sxs-lookup"><span data-stu-id="98eac-109">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="98eac-110">フロントエンドサーバーで Lync Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="98eac-110">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="98eac-111">コマンド プロンプトで、次の各コマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="98eac-111">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="98eac-112">Windows Live Messenger は、音声ビデオの暗号化をサポートしていないため、この手順は必ず実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98eac-112">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="98eac-113">このコマンドは、音声ビデオ データの暗号化を必須にするのではなく、グローバル ポリシーの暗号化設定を「サポート」に設定します。</span><span class="sxs-lookup"><span data-stu-id="98eac-113">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="98eac-114">暗号化をサポートするクライアントは、Lync 2013 などの暗号化を引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="98eac-114">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

