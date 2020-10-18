---
title: 'Lync Server 2013: Lync Phone Edition 構成設定情報の表示'
description: 'Lync Server 2013: Lync Phone Edition 構成設定情報を表示します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62719b24920ee72a92b2f80498d5ea2a59288c2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576433"
---
# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a>Lync Server 2013 での Lync Phone Edition の構成設定情報の表示

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

Lync Phone Edition を実行しているデバイスに関する構成情報を表示できます。 情報はコレクションにまとめられています。 Lync Server をインストールすると、展開で Lync Phone Edition を実行しているすべてのデバイスに適用される Lync Phone Edition の設定のコレクションが取得されます。 特定のサイトに対して、設定の新しいコレクションを作成することもできます。 サイト設定は、グローバル設定より優先されます。 設定の各コレクションは、名前、スコープ (グローバルまたはサイト)、SIP セキュリティ設定、ログ レベル、音声のサービス品質 (QoS) レベル、電話ロック設定、および電話ロックの詳細 (ロック解除の暗証番号 (PIN) の最小桁数および電話が自動ロックされるまでの時間) で構成されています。

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a>Lync Phone Edition を実行しているデバイスに関する構成情報を表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**クライアント**] をクリックし、[**デバイスの構成**] 移動ボタンをクリックします。

4.  [**デバイスの構成**] ページで、情報を表示する設定のコレクションをクリックします。名前、スコープ、SIP セキュリティ設定、音声の品質レベル、および電話ロック設定がメイン ページに表示されます。ログ レベルと電話ロックの詳細を表示するには、[**編集**] メニューをクリックし、[**詳細の表示**] をクリックします。

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して Lync Phone Edition の構成情報を表示する

Lync Server 管理シェルと **get-csucphoneconfiguration** コマンドレットを使用して、Lync Phone Edition の構成設定を表示できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a>Lync Phone Edition の構成情報を表示するには

  - すべての Lync Phone Edition 構成設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、ENTER キーを押します。
    
        Get-CsUCPhoneConfiguration
    
    コマンドを実行すると、次のような情報が返されます。
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

詳細については、「 [get-csucphoneconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の Lync Phone Edition 構成設定のコレクションを作成または変更する](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[Lync Server 2013 の Lync Phone Edition 構成設定の既存コレクションの削除](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Lync Server 2013 で Lync Phone Edition のセキュリティ設定を構成する](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Lync Server 2013 での電話ロックの適用](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

