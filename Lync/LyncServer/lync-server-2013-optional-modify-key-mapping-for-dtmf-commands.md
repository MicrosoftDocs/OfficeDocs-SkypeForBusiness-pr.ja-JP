---
title: 'Lync Server 2013: (オプション) DTMF コマンドの主要なマッピングを変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd1a9fbe17a07403fbf0195026d44b490680973e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a>(オプション) Lync Server 2013 で DTMF コマンドの主要なマッピングを変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-30_

ダイヤルイン会議のユーザーは、電話キーパッドのキーを押して、デュアルトーン多重周波数 (DTMF) のコマンドを実行できます。 DTMF コマンドを使用すると、会議にダイヤルインするユーザーは、電話のキーパッドを使用して会議設定 (自身をミュートおよびミュート解除したり、会議をロックおよびロック解除したりするなど) を制御できます。 コマンドレットを使用して、DTMF コマンドに使用されるキーを変更できます。 この手順は省略可能です。

<div>


> [!NOTE]  
> これらのコマンドレットと、使用可能な DTMF オプションの詳細については、「Lync Server 管理シェルのドキュメント」または「Lync Server 管理シェルのコマンドラインのヘルプ」を参照してください。



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a>DTMF コマンドのキーマッピングを変更するには

1.  **RTCUniversalServerAdmins**グループのメンバーとして、または**Cs-Serveradministrator**または**csadministrator**の役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  コマンド プロンプトで次のコマンドを実行します。
    
        Get-CsDialinConferencingDtmfConfiguration
    
    このコマンドレットは、ダイヤルイン会議で使用される DTMF 設定を返します。

4.  次のコマンドレットを実行し、変更する各オプションに対して押すキーを指定します。
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    このコマンドレットは、ダイヤルイン会議で使用される DTMF 設定を変更します。
    
    次に例を示します。
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    次の例では、押されたキーを入れ替えて、アナウンスメントを有効または無効にします。キーを押すと、すべての参加者をミュートおよびミュート解除することができます。 Id が指定されていないため、これらの変更はグローバルな DTMF 設定に適用されます。

5.  (オプション) 特定サイトに対する DTMF コマンドの追加セットを作成するには、サイト ID と **New-CsDialinConferencingDtmfConfiguration** コマンドレットを使用します。 サイトの新たな DTMF 設定を作成すると、そのサイト設定はグローバル設定よりも優先されるようになります。 詳細については、「Lync Server 管理シェルのドキュメント」または「Lync Server 管理シェルのコマンドラインのヘルプ」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

