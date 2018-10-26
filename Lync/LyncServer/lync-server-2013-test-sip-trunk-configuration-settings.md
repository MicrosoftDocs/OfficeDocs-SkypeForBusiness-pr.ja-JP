---
title: SIP トランク構成設定のテスト
TOCTitle: SIP トランク構成設定のテスト
ms:assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721880(v=OCS.15)
ms:contentKeyID: 49887142
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# SIP トランク構成設定のテスト

 

_**トピックの最終更新日:** 2012-11-01_

SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係および機能を定義します。たとえば、次の設定ができます。

  - トランクでメディア バイパスを有効化するか。

  - Real-time Transport Control Protocol (RTCP) パケットが送信される条件。

  - 各トランクでセキュア リアルタイム プロトコル (SRTP) 暗号化を要求するか。

Microsoft Lync Server 2013 をインストールすると、SIP トランクの構成設定のグローバル コレクションが作成されます。また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。管理者は、Test-CsTrunkConfiguration コマンドレットを使用して、ユーザーがダイヤルした番号をゲートウェイで処理可能な番号にトランクが変換できるかどうかも確認できます。

トランク構成設定は、Windows PowerShell と [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) コマンドレットを使用する方法でのみテストできます。このコマンドレットは、Lync Server 2013 管理シェル から、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## トランク構成設定のテスト

  - このコマンドを実行すると、ダイヤルされた番号 4255551212 がレドモンド サイトのトランク構成設定によって正しく変換できることを確認できます。
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

