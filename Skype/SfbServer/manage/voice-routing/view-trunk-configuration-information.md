---
title: Skype for Business Server でトランク構成情報を表示する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: SIP トランク構成設定は、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ、IP パブリックブランチ交換 (PBX)、またはサービスプロバイダのセッションボーダーコントローラー (SBC) 間の関係と機能を定義します。
ms.openlocfilehash: dd8bd94bb8831fc3e406bed46015b2d955a2359c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274871"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Skype for Business Server でトランク構成情報を表示する

SIP トランク構成設定は、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ、IP パブリックブランチ交換 (PBX)、またはサービスプロバイダのセッションボーダーコントローラー (SBC) 間の関係と機能を定義します。

- トランクでメディア バイパスを有効化するか。
- リアルタイム伝送制御プロトコル (RTCP) パケットを送信する条件。
- 各トランクで、セキュリティで保護されたリアルタイムプロトコル (SRTP) 暗号化が必要かどうかを示します。

Skype for Business Server をインストールすると、SIP トランク構成設定のグローバルコレクションが作成されます。 また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。

**Skype for Business Server コントロールパネルを使用して SIP トランクの構成情報を表示するには**

1. Skype for Business Server コントロールパネルで、[**音声ルーティング**] をクリックし、[ **Trunk 構成**] をクリックします。
2. [**トランクの構成**] タブに、すべてのトランク構成設定のコレクションの一覧が表示されます。各コレクションについて、**名前**、**スコープ**、**状態**、**メディアバイパス**の各プロパティの値と、 **PSTN 使用**量、**通話番号ルール**、関連付けられている**番号ルール**の数が表示されます。コレクションを使用します。 トランク構成設定のコレクションに関する追加情報を表示するには、目的のコレクションをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。 一度に1つのトランク構成設定のコレクションについてのみ、詳細情報を表示できます。

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用した SIP トランク構成情報の表示

SIP トランク構成設定は、Skype for Business Server PowerShell と Set-cstrunkconfiguration コマンドレットを使用して表示できます。 このコマンドレットは、Skype for Business Server 管理シェルから、またはリモートセッション Windows PowerShell から実行できます。 リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法について詳しくは、「Lync Server Windows PowerShell のブログ記事」をご覧ください。「クイックhttp://go.microsoft.com/fwlink/p/?linkId=255876スタート: リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。 このリンクを置換または削除します。


**SIP トランクの構成情報を表示するには**

SIP トランク構成のすべての設定に関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力して、enter キーを押します。

`Get-CsTrunkConfiguration`

次のような情報が表示されます。

```
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
詳細については、 [set-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration)コマンドレットのヘルプトピックを参照してください。



