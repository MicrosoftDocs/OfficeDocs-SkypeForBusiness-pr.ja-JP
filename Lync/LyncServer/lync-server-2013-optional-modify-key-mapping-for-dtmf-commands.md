---
title: 'Lync Server 2013: (オプション) DTMF コマンドのキーマッピングを変更する'
description: 'Lync Server 2013: (オプション) DTMF コマンドのキーマッピングを変更します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7581001c31d929163962378a8734435f6d07c6c8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565793"
---
# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a>オプションLync Server 2013 での DTMF コマンドのキーマッピングの変更

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-30_

ダイヤルイン会議のユーザーは、電話キーパッドのキーを押して、デュアルトーン多重周波数 (DTMF) のコマンドを実行できます。 DTMF コマンドを使用すると、会議にダイヤルインするユーザーは、電話のキーパッドを使用して会議設定 (自身をミュートおよびミュート解除したり、会議をロックおよびロック解除したりするなど) を制御できます。 コマンドレットを使用して、DTMF コマンドに使用されるキーを変更できます。このステップはオプションです。

<div>


> [!NOTE]  
> これらのコマンドレットおよび使用可能な DTMF オプションの詳細については、「Lync Server Management Shell documentation or Lync Server Management Shell コマンドラインヘルプ」を参照してください。



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a>DTMF コマンドのキー マッピングを変更するには

1.  コンピューターに **RTCUniversalServerAdmins** グループのメンバーとしてログオンするか、**Cs-ServerAdministrator** または **CsAdministrator** 役割のメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  コマンド プロンプトで次のコマンドを実行します。
    
        Get-CsDialinConferencingDtmfConfiguration
    
    このコマンドレットを実行すると、ダイヤルイン会議に使用される DTMF 設定が戻されます。

4.  次のコマンドレットを実行し、変更対象である各オプションで押されるキーを指定します。
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    このコマンドレットを実行すると、ダイヤルイン会議に使用される DTMF 設定が変更されます。
    
    次にその例を示します。
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    この例では、アナウンスを有効/無効にするために押されるキーと、全参加者のミュート/ミュート解除のために押されるキーを交換します。 ID が指定されていないため、これらの変更はグローバル DTMF 設定に適用されます。

5.  (オプション) 特定サイトに対する DTMF コマンドの追加セットを作成するには、サイト ID と **New-CsDialinConferencingDtmfConfiguration** コマンドレットを使用します。 サイトの新たな DTMF 設定を作成すると、そのサイト設定はグローバル設定よりも優先されるようになります。 詳細については、「Lync Server Management Shell documentation」または「Lync Server Management Shell コマンドラインヘルプ」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

