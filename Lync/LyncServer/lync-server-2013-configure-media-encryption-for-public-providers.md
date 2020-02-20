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
ms.openlocfilehash: 571aa8309ee310353adebecfc7b8fe737076b384
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a>Lync Server 2013 のパブリックプロバイダーに対するメディアの暗号化の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-12-12_

Windows Live Messenger で音声ビデオ (A/V) フェデレーションを実装している場合は、Lync Server の暗号化レベルと EnablePublicCloudAccess ポリシーの2つのパラメーターを変更する必要があります。 既定では、暗号化レベルは「必須」です。 この設定を「サポート」に変更する必要があります。 EnablePublicCloudAccess ポリシーが false に設定されている場合は、**True** に変更する必要があります。 これは、Lync Server 管理シェルから実行できます。

<div>

## <a name="configure-federation-for-windows-live"></a>Windows Live のフェデレーションを構成する

1.  フロントエンドサーバーで Lync Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  コマンド プロンプトで、次の各コマンドを入力します。
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > Windows Live Messenger は、音声ビデオの暗号化をサポートしていないため、この手順は必ず実行する必要があります。 このコマンドは、音声ビデオ データの暗号化を必須にするのではなく、グローバル ポリシーの暗号化設定を「サポート」に設定します。 暗号化をサポートするクライアントは、Lync 2013 などの暗号化を引き続き使用します。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

