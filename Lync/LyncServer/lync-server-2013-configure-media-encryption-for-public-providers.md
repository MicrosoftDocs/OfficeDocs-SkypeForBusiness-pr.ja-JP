---
title: 'Lync Server 2013: 公開プロバイダーに対するメディアの暗号化の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 270035730b8268c56b1730d8c212e90c8a9f1a30
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="b6d97-102">Lync Server 2013 での公開プロバイダーに対するメディアの暗号化の構成</span><span class="sxs-lookup"><span data-stu-id="b6d97-102">Configure media encryption for public providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6d97-103">_**最終更新日:** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="b6d97-103">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="b6d97-104">音声/ビデオ (A/V) フェデレーションを Windows Live Messenger と共に実装する場合は、Lync Server の暗号化レベルと EnablePublicCloudAccess ポリシーという2つのパラメーターを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6d97-104">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="b6d97-105">既定では、暗号化レベルは [必須] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="b6d97-105">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="b6d97-106">この設定は、"サポート" に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6d97-106">You must change this setting to Supported.</span></span> <span data-ttu-id="b6d97-107">EnablePublicCloudAccess ポリシーが false に設定されている場合は、 **True**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6d97-107">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="b6d97-108">これは、Lync Server 管理シェルから行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b6d97-108">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="b6d97-109">Windows Live 用フェデレーションを構成する</span><span class="sxs-lookup"><span data-stu-id="b6d97-109">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="b6d97-110">フロントエンドサーバーで Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6d97-110">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b6d97-111">コマンドプロンプトで、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b6d97-111">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="b6d97-112">Windows Live Messenger では音声/ビデオの暗号化がサポートされていないため、これは必須の手順です。</span><span class="sxs-lookup"><span data-stu-id="b6d97-112">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="b6d97-113">このコマンドは、オーディオ/ビデオデータの暗号化を必要とするのではなく、グローバルポリシーをサポート暗号化設定に設定します。</span><span class="sxs-lookup"><span data-stu-id="b6d97-113">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="b6d97-114">暗号化をサポートするクライアントでも、Lync 2013 などの暗号化が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b6d97-114">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

