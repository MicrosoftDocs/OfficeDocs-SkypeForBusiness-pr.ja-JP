---
title: Skype のビジネス サーバーのトランクの構成情報を表示します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: SIP トランクの構成設定は、仲介サーバーおよび公衆交換電話網 (PSTN) ゲートウェイ、IP 公開ブランチ交換機 (PBX)、またはサービス プロバイダーのセッション ボーダー コント ローラー (SBC) の間での機能との関係を定義します。
ms.openlocfilehash: 6ba97fa4650b8d62be625256ff4d3b9a3bb7cc68
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892166"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Skype のビジネス サーバーのトランクの構成情報を表示します。

SIP トランクの構成設定は、仲介サーバーおよび公衆交換電話網 (PSTN) ゲートウェイ、IP 公開ブランチ交換機 (PBX)、またはサービス プロバイダーのセッション ボーダー コント ローラー (SBC) の間での機能との関係を定義します。

- トランクでメディア バイパスを有効化するか。
- リアルタイム転送制御プロトコル (RTCP) パケットを送信する条件です。
- かどうか各トランクには、セキュリティで保護されたリアルタイム プロトコル (SRTP) 暗号化が必要です。

ビジネス サーバーの Skype をインストールすると SIP トランク構成設定のグローバル コレクションが作成されます。 また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。

**ビジネス サーバーのコントロール パネルの Skype を使用して、SIP トランクの構成情報を表示するのには**

1. [ビジネス サーバーのコントロール パネルの Skype、**音声ルーティング**を**トランク構成**] をクリックします。
2. [**トランク構成**] タブですべてのトランク構成設定コレクションの一覧が表示されます。コレクションごとに、**名前**、**範囲**、**状態**、および**メディアをバイパス**プロパティの値と、 **PSTN の使用法****規則の番号を呼び出し**、および**番号の規則と呼ばれる**関連付けられている数が表示されます。コレクションです。 トランク構成設定のコレクションの詳細情報を表示するには、目的のコレクションをクリックして**編集**を**の詳細を表示**] をクリックします。 一度にトランク構成設定の 1 つのコレクションに対してのみ詳細情報を表示できることに注意してください。

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して SIP トランクの構成情報を表示します。

SIP トランクの構成設定は、Skype をビジネス サーバー PowerShell および Get CsTrunkConfiguration コマンドレットを使用して表示できます。 ビジネス サーバー管理シェルの Skype から、または Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。 ビジネス サーバーでは、Skype に接続するリモートの Windows PowerShell を使用して詳細に Lync Server の Windows PowerShell のブログ記事「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」を参照してくださいhttp://go.microsoft.com/fwlink/p/?linkId=255876。 置き換えるか、このリンクを削除します。


**SIP トランクの構成情報を表示するのには**

すべての SIP トランク構成設定に関する情報を表示するのには、Skype のビジネス サーバー管理シェルには、次のコマンドを入力し、ENTER キーを押します。

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
詳細については、 [Get CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration)コマンドレットのヘルプ トピックを参照してください。



