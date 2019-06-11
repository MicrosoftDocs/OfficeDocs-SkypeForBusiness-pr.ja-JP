---
title: 'Lync Server 2013: トランク構成情報の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View trunk configuration information
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49733862
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abf496382ed33b95e8de9f387a8623fb0984ed28
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-trunk-configuration-information-in-lync-server-2013"></a>Lync Server 2013 でのトランク構成情報の表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-22_

SIP トランク構成設定は、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ、IP パブリックブランチ交換 (PBX)、またはサービスプロバイダのセッションボーダーコントローラー (SBC) 間の関係と機能を定義します。 たとえば、次の設定ができます。

  - トランクでメディア バイパスを有効化するか。

  - リアルタイム伝送制御プロトコル (RTCP) パケットを送信する条件。

  - 各トランクで、セキュリティで保護されたリアルタイムプロトコル (SRTP) 暗号化が必要かどうかを示します。

Microsoft Lync Server 2013 をインストールすると、SIP トランク構成設定のグローバルコレクションが作成されます。 また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用して SIP トランクの構成情報を表示するには

1.  Lync Server コントロールパネルで、[**音声ルーティング**] をクリックし、[**トランク構成**] をクリックします。

2.  [**トランクの構成**] タブに、すべてのトランク構成設定のコレクションの一覧が表示されます。各コレクションについて、**名前**、**スコープ**、**状態**、**メディアバイパス**の各プロパティの値と、 **PSTN 使用**量、**通話番号ルール**、関連付けられている**番号ルール**の数が表示されます。コレクションを使用します。 トランク構成設定のコレクションに関する追加情報を表示するには、目的のコレクションをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。 一度に1つのトランク構成設定のコレクションについてのみ、詳細情報を表示できます。

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用した SIP トランク構成情報の表示

SIP トランク構成設定は、Lync Server PowerShell と Set-cstrunkconfiguration コマンドレットを使用して表示できます。 このコマンドレットは、Lync Server 2013 Management Shell またはリモートセッション Windows PowerShell から実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-view-sip-trunk-configuration-information"></a>SIP トランクの構成情報を表示するには

  - SIP トランク構成のすべての設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力して、enter キーを押します。
    
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

</div>

詳細については、 [set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

