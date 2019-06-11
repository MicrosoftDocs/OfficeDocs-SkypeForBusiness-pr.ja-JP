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
ms.openlocfilehash: 1496bda01456593066efd212241e3d930f1e2cc6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a>Lync Server 2013 での公開プロバイダーに対するメディアの暗号化の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-12-12_

音声/ビデオ (A/V) フェデレーションを Windows Live Messenger と共に実装する場合は、Lync Server の暗号化レベルと EnablePublicCloudAccess ポリシーという2つのパラメーターを変更する必要があります。 既定では、暗号化レベルは [必須] に設定されています。 この設定は、"サポート" に変更する必要があります。 EnablePublicCloudAccess ポリシーが false に設定されている場合は、 **True**に設定する必要があります。 これは、Lync Server 管理シェルから行うことができます。

<div>

## <a name="configure-federation-for-windows-live"></a>Windows Live 用フェデレーションを構成する

1.  フロントエンドサーバーで Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  コマンドプロンプトで、次のコマンドを入力します。
    
       ```
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > Windows Live Messenger では音声/ビデオの暗号化がサポートされていないため、これは必須の手順です。 このコマンドは、オーディオ/ビデオデータの暗号化を必要とするのではなく、グローバルポリシーをサポート暗号化設定に設定します。 暗号化をサポートするクライアントでも、Lync 2013 などの暗号化が使用されます。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

