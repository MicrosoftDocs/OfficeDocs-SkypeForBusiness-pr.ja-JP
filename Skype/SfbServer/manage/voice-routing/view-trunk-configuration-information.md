---
title: '[トランク構成情報] を [Skype for Business Server'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係および機能を定義します。
ms.openlocfilehash: b27e3dd72e7a4aebee907541b1ec0250cf7cfd3f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778257"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>[トランク構成情報] を [Skype for Business Server

SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係および機能を定義します。

- トランクでメディア バイパスを有効化するか。
- Real-time Transport Control Protocol (RTCP) パケットが送信される条件。
- 各トランクでセキュア リアルタイム プロトコル (SRTP) 暗号化を要求するか。

サーバーをインストールSkype for Business Server、SIP トランク構成設定のグローバル コレクションが作成されます。 また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。

**コントロール パネルを使用して SIP トランク構成情報Skype for Business Serverするには**

1. [コントロール Skype for Business Server] で、[音声ルーティング]**を** クリックし、[トランク構成]**をクリックします**。
2. [トランク **構成] タブ** に、すべてのトランク構成設定コレクションの一覧が表示されます。各コレクションには、**名前**、**スコープ**、状態、およびメディアバイパス プロパティの値と **、PSTN** 使用法の数、電話番号ルール、およびコレクションに関連付けられた呼び出し番号ルールが表示されます。 トランク構成設定のコレクションの詳細を表示するには、関心のあるコレクションをクリックし、[編集] をクリックし、[詳細の表示]**をクリックします**。 一度に 1 つのトランク構成設定のコレクションについてのみ詳細情報を表示できます。

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>SIP トランク構成情報を表示する場合は、Windows PowerShellコマンドレットを使用します。

SIP トランク構成設定は、PowerShell および Skype for Business ServerコマンドレットをGet-CsTrunkConfigurationできます。 このコマンドレットは、管理シェルからSkype for Business Serverリモート セッション から実行Windows PowerShell。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、Lync Server Windows PowerShell ブログ記事「クイック スタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理」を https://go.microsoft.com/fwlink/p/?linkId=255876 参照してください。 このリンクを置換または削除します。


**SIP トランク構成情報を表示するには**

すべての SIP トランク構成設定に関する情報を表示するには、次のコマンドを [管理シェル] Skype for Business Server入力し、Enter キーを押します。

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
詳細については [、Get-CsTrunkConfiguration](/powershell/module/skype/Get-CsTrunkConfiguration) コマンドレットのヘルプ トピックを参照してください。