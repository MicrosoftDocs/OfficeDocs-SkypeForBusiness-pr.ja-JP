---
title: 'Lync Server 2013: Lync Phone Edition の構成設定の情報を表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 213b9775b22818c34eb8f7896ea02a4872182a42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a>Lync Server 2013 で Lync Phone Edition の構成設定の情報を表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

Lync Phone Edition を実行しているデバイスに関する構成情報を表示できます。 情報はコレクションに整理されます。 Lync Server をインストールすると、展開で Lync Phone Edition を実行しているすべてのデバイスに適用される Lync Phone エディション設定のコレクションを取得できます。 また、特定のサイトの設定の新しいコレクションを作成することもできます。 サイトの設定はグローバル設定よりも優先されます。 設定の各コレクションは、名前、スコープ (グローバルまたはサイト)、SIP セキュリティ設定、ログレベル、音声品質サービス (QoS) レベル、電話ロック設定、および電話ロックの詳細 (ロック解除の個人識別の最小文字数) で構成されます。電話がロックされるまでの番号 (PIN) と時刻。

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a>Lync Phone Edition を実行しているデバイスに関する構成情報を表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイス構成**] ナビゲーションボタンをクリックします。

4.  [**デバイスの構成**] ページで、情報を表示する設定のコレクションをクリックします。 名前、スコープ、SIP セキュリティ設定、音声品質レベル、および電話ロックの設定が、メインページに表示されます。 ログレベルと電話ロックの詳細を表示するには、[**編集**] メニューをクリックし、[**詳細の表示**] をクリックします。

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用した Lync Phone Edition 構成情報の表示

Lync Server 管理シェルと**CsUCPhoneConfiguration**コマンドレットを使用して、Lync Phone Edition の構成設定を表示できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a>Lync Phone Edition の構成情報を表示するには

  - すべての Lync Phone エディションの構成設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsUCPhoneConfiguration
    
    このコマンドは、次のような情報を返します。
    
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

詳細については、「 [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で Lync Phone エディションの構成設定のコレクションを作成または変更する](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[Lync Server 2013 で既存の Lync Phone エディション構成の設定を削除する](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Lync Server 2013 で Lync Phone Edition のセキュリティ設定を構成する](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Lync Server 2013 での電話のロックを適用する](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

