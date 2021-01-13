---
title: Skype for Business Server でのトランク構成情報の表示
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係および機能を定義します。
ms.openlocfilehash: c473c3fc19138ac91b44dff8552555418d36533f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826167"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Skype for Business Server でのトランク構成情報の表示

SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係および機能を定義します。

- トランクでメディア バイパスを有効化するか。
- Real-time Transport Control Protocol (RTCP) パケットが送信される条件。
- 各トランクでセキュア リアルタイム プロトコル (SRTP) 暗号化を要求するか。

Skype for Business Server をインストールすると、SIP トランク構成設定のグローバル コレクションが自動的に作成されます。 また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。

**Skype for Business Server コントロール パネルを使用して SIP トランク構成情報を表示するには**

1. Skype for Business Server コントロール パネルで、[音声ルーティング] **をクリックし**、[トランク構成] を **クリックします**。
2. [トランク **構成]** タブには、すべてのトランク構成設定コレクションの一覧が表示されます。各コレクションには、名前、**スコープ**、状態、およびメディア のバイパスプロパティの値と **、PSTN** 使用法の数、呼び出し元番号のルール、およびコレクションに関連付けられている呼び出し番号のルールが表示されます。  トランク構成設定のコレクションに関するその他の詳細を表示するには、関心のあるコレクションをクリックし、[編集] をクリックして、[詳細の表示]**をクリックします**。 詳細情報は、一度に 1 つのトランク構成設定のコレクションについてのみ表示できます。

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>SIP トランク構成情報の表示 (Windows PowerShellコマンドレットを使用)

SIP トランク構成設定は、Skype for Business Server PowerShell と Get-CsTrunkConfiguration使用して表示できます。 このコマンドレットは、Skype for Business Server 管理シェルまたはリモート セッション サーバーから実行Windows PowerShell。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、Lync Server Windows PowerShell ブログ記事「クイック スタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理」を参照してください。 https://go.microsoft.com/fwlink/p/?linkId=255876 このリンクを置換または削除します。


**SIP トランク構成情報を表示するには**

すべての SIP トランク構成設定に関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、Enter キーを押します。

```powershell
Get-CsTrunkConfiguration
```

次のような情報が表示されます。

```console
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
```
詳細については [、Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) コマンドレットのヘルプ トピックを参照してください。



