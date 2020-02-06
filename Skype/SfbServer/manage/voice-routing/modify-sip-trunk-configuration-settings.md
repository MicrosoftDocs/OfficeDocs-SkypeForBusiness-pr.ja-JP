---
title: Skype for Business Server で SIP トランクの設定を変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'SIP トランク構成設定は、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ、IP パブリックブランチ交換 (PBX)、またはサービスプロバイダのセッションボーダーコントローラー (SBC) 間の関係と機能を定義します。 '
ms.openlocfilehash: 76196df2cf0bd74ef804a082862891c326048408
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816957"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server で SIP トランクの設定を変更する

SIP トランク構成設定は、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ、IP パブリックブランチ交換 (PBX)、またはサービスプロバイダのセッションボーダーコントローラー (SBC) 間の関係と機能を定義します。 たとえば、次の設定ができます。

- トランクでメディア バイパスを有効化するか。
- リアルタイム伝送制御プロトコル (RTCP) パケットを送信する条件。
- 各トランクで、セキュリティで保護されたリアルタイムプロトコル (SRTP) 暗号化が必要かどうかを示します。

Skype for Business Server をインストールすると、SIP トランク構成設定のグローバルコレクションが作成されます。 また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。 これらのコレクションのいずれかは、後で Skype for Business Server コントロールパネルまたは Windows PowerShell を使って変更できます。

Skype for Business Server Server のコントロールパネルを使用して SIP トランクの設定を変更する場合は、次のオプションを利用できます。

|UI 設定 |PowerShell パラメーター |説明 |
|--|--|--|
|名前|ID|コレクションの一意の識別子。このプロパティは読み取り専用です。トランク構成設定のコレクションの Identity は変更できません。|
|説明|説明|管理者が、設定に関する追加情報を格納できます (たとえば、トランク構成の目的)。|
|サポートされる最大初期ダイアログの数|MaxEarlyDialogs|サービス プロバイダーの PSTN ゲートウェイ、IP-PBX、または SBC が、仲介サーバーに送信した INVITE に対して受信できる分岐応答の最大数です。|
|暗号化サポート レベル|SRTPMode|仲介サーバーと、サービス プロバイダーの PSTN ゲートウェイ、IP-PBX、または SBC 間のメディア トラフィックを保護するためのサポート レベルを示します。 メディア バイパスの場合、この値はメディア構成の EncryptionLevel 設定と互換性を持つ必要があります。 メディア構成は、CsMediaConfiguration コマンドレットと CsMediaConfiguration コマンドレットを使用して設定されます。<br/>有効な値は次のとおりです。<br/><br/>**必須**: srtp 暗号化を使用する必要があります。<br/>**オプション**: srtp は、ゲートウェイがサポートしている場合に使用されます。<br/>サポートされて**いませ**ん: srtp 暗号化はサポートされていないため、使用されません。<br/><br/>SRTPMode は、ゲートウェイがトランスポート層セキュリティ (TLS) プロトコルを使用するよう構成されている場合にのみ使用されます。ゲートウェイがトランスポートとして伝送制御プロトコル (TCP) を使用するように構成されている場合は、SRTPMode は内部で Not Supported に設定されます。|
|サポートの参照|Enable3pccRefer<br/>EnableReferSupport|[**ゲートウェイへの参照の送信を有効にする**] に設定した場合、トランクが仲介サーバーからの REFER 要求の受信をサポートすることを示します。<br/>[**サードパーティ通話コントロールを使用する参照を有効にする**] に設定すると、3PCC プロトコルを使用して転送される通話がホストされたサイトをバイパスできるようにすることを示します。3PCC は、「三者間通話コントロール」とも呼ばれ、第三者を使用して二人の通話者を接続するとき (たとえば、オペレーターが人物 A から人物 B への通話を接続するとき) に使用します。|
|メディアのバイパスを有効にする|EnableBypass|メディア バイパスがこのトランクに対して有効かどうかを示します。メディア バイパスは、[**集中メディア処理**] も有効になっている場合にのみ有効にできます。|
|集中メディア処理|ConcentratedTopology|既知のメディア終端ポイントがあるかどうかを示します (既知のメディア終端ポイントの例として、メディア終端が信号終端と同じ IP を持つ PSTN ゲートウェイがあります)。|
|RTP ラッチを有効にする|EnableRTPLatching|SIP トランクが RTP ラッチをサポートするかどうかを示します。RTP ラッチは、NAT (ネットワーク アドレス変換) 装置またはファイアウォールを経由した RTP/RTCP 接続を可能にする技術です。|
|着信転送履歴を有効にする|ForwardCallHistory|通話履歴の情報をトランク経由で転送するかどうかを指定します。|
|P-Asserted-Identity データの転送を有効にする|ForwardPAI|P-Asserted-Identity (PAI) ヘッダーを通話とともに転送するかどうかを示します。PAI ヘッダーがあれば、発信者 ID を確認できます。|
|送信ルーティング フェールオーバー タイマーを有効にする|EnableFastFailoverTimer|発信通話が 10 秒以内にゲートウェイによって応答されない場合に次に使用できるトランクにルーティングするかどうかを示します。他にトランクがない場合は、通話は自動的に破棄されます。ネットワークおよびゲートウェイの応答が遅い環境の場合、通話が不必要に破棄されるようになる可能性があります。|
|関連付けられている PSTN 使用法|PSTNUsages|トランクに割り当てられた PSTN 使用法のコレクションです。|
|テストする変換後の番号|該当なし|トランクの構成設定の臨時テストを行うために使用できる電話番号です。|
|関連付けられている変換ルール|OutboundTranslationRulesList|発信ルーティングによって処理される通話 (PBX または PSTN の宛先にルーティングされる通話) に適用される、電話番号変換ルールのコレクションです。|
|着信者番号の変換ルール|OutboundCallingNumberTranslationRulesList|トランクに割り当てられた発信電話番号の変換ルールのコレクションです。|
|テストする電話番号|該当なし|変換ルールの臨時テストを行うために使用できる電話番号です。|
|発信者番号|該当なし|テストする電話番号が発信者の電話番号であることを示します。|
|着信者番号|該当なし|テストする電話番号が着信者の電話番号であることを示します。|
|||

> [!Note]
> Skype for Business Server の Set-cstrunkconfiguration コマンドレットでは、Skype for Business Server コントロールパネルに表示されない追加プロパティをサポートしています。 詳細については、 [set-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTrunkConfiguration)コマンドレットのヘルプトピックを参照してください。 

**Skype for Business Server コントロールパネルを使用して SIP トランクの設定を変更するには**

1. Skype for Business Server コントロールパネルで、[**音声ルーティング**] をクリックし、[ **Trunk 構成**] をクリックします。
2. [**トランク構成**] タブで、変更するトランク構成の設定をダブルクリックします。編集できる設定のコレクションは一度に 1 つだけです。複数のコレクションで同じ変更を行う場合は、Windows PowerShell を使用してください。
3. [**トランク構成の編集**] ダイアログボックスで、適切な選択を行い、[ **OK]** をクリックします。
4. コレクションの [状態] プロパティが、[コミットされていません] に変わります。 変更をコミットしてコレクションを削除するには、[**コミット**] をクリックし、[**すべてコミット**] をクリックします。
5. [コミットされていない**音声構成の設定**s] ダイアログボックスで、[ **OK**] をクリックします。
6. [ **Skype For Business Server コントロールパネル**] ダイアログボックスで、[ **OK**] をクリックします。
