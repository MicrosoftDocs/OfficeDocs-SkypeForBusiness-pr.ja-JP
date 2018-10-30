---
title: トランク構成情報の表示
TOCTitle: トランク構成情報の表示
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49887200
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# トランク構成情報の表示

 

_**トピックの最終更新日:** 2013-02-22_

SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係および機能を定義します。たとえば、次の設定ができます。

  - トランクでメディア バイパスを有効化するか。

  - Real-time Transport Control Protocol (RTCP) パケットが送信される条件。

  - 各トランクでセキュア リアルタイム プロトコル (SRTP) 暗号化を要求するか。

Microsoft Lync Server 2013 をインストールすると、SIP トランクの構成設定のグローバル コレクションが作成されます。また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。

## Lync Server コントロール パネルを使用した SIP トランク構成情報の表示

1.  Lync Server コントロール パネル で \[**音声ルーティング**\] をクリックし、\[**トランク構成**\] をクリックします。

2.  \[**トランク構成**\] タブには、すべてのトランク構成設定のコレクションの一覧が表示されます。各コレクションには、\[**名前**\]、\[**範囲**\]、\[**状態**\]、および \[**メディア バイパス**\] プロパティの値と共に、コレクションに関連付けられた \[**PSTN 使用法**\]、\[**Calling number rules**\] (発信元番号のルール)、および \[**Called number rules**\] (発信先番号のルール) の数が表示されます。トランク構成設定のコレクションについてさらに詳細を表示するには、対象のコレクションをクリックし、\[**編集**\] をクリックして、\[**詳細の表示**\] をクリックします。詳細情報を表示できるのは、一度につき 1 つのトランク構成設定コレクションのみです。

## Lync Server PowerShell コマンドレットを使用した SIP トランク構成情報の表示

SIP トランク構成設定は、Lync Server PowerShell と Get-CsTrunkConfiguration コマンドレットを使用して表示することもできます。このコマンドレットは、Lync Server 2013 管理シェル またはリモート セッションの Windows PowerShell から実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## SIP トランク構成情報の表示

  - すべての SIP トランク構成設定に関する情報を表示するには、Lync Server 管理シェル で次のコマンドを入力して Enter キーを押します。
    
        Get-CsTrunkConfiguration
    
    次のような情報が表示されます。
    
        Identity                                  : Global
        OutboundTranslationRulesList              : {}
        SipResponseCodeTranslationRulesList       : {}
        OutboundCallingNumberTranslationRulesList : {}
        PstnUsages                                : {}
        Description                               :
        ConcentratedTopology                      : True
        EnableBypass                              : False
        EnableMobileTrunkSupport                  : False
        EnableReferSupport                        : True
        EnableSessionTimer                        : False
        EnableSignalBoost                         : False
        MaxEarlyDialogs                           : 20
        RemovePlusFromUri                         : False
        RTCPActiveCalls                           : True
        RTCPCallsOnHold                           : True
        SRTPMode                                  : Required
        EnablePIDFLOSupport                       : False
        EnableRTPLatching                         : False
        EnableOnlineVoice                         : False
        ForwardCallHistory                        : False
        Enable3pccRefer                           : False
        ForwardPAI                                : False
        EnableFastFailoverTimer                   : True

詳細については、[Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) コマンドレットのヘルプ トピックを参照してください。

