---
title: Skype for Business Server での SIP トランク構成設定の変更
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
description: 'SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係および機能を定義します。 '
ms.openlocfilehash: a4c91d447fd61a2763fcabce492e4f85f88cb538
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827727"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server での SIP トランク構成設定の変更

SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係および機能を定義します。たとえば、次の設定ができます。

- トランクでメディア バイパスを有効化するか。
- Real-time Transport Control Protocol (RTCP) パケットが送信される条件。
- 各トランクでセキュア リアルタイム プロトコル (SRTP) 暗号化を要求するか。

Skype for Business Server をインストールすると、SIP トランク構成設定のグローバル コレクションが自動的に作成されます。 また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。 これらのコレクションは、後で Skype for Business Server コントロール パネルまたはデバイス を使用して変更Windows PowerShell。

Skype for Business Server コントロール パネルを使用して SIP トランク構成設定を変更する場合は、次のオプションを使用できます。

|UI 設定 |PowerShell パラメーター |説明 |
|--|--|--|
|名前|ID|コレクションの一意の識別子。このプロパティは読み取り専用です。トランク構成設定のコレクションの Identity は変更できません。|
|説明|説明|管理者が、設定に関する追加情報を格納できます (たとえば、トランク構成の目的)。|
|サポートされる最大初期ダイアログの数|MaxEarlyDialogs|サービス プロバイダーの PSTN ゲートウェイ、IP-PBX、または SBC が、仲介サーバーに送信した INVITE に対して受信できる分岐応答の最大数です。|
|暗号化サポート レベル|SRTPMode|仲介サーバーと、サービス プロバイダーの PSTN ゲートウェイ、IP-PBX、または SBC 間のメディア トラフィックを保護するためのサポート レベルを示します。 メディア バイパスの場合、この値はメディア構成の EncryptionLevel 設定と互換性を持つ必要があります。 メディア構成は、次のコマンドレットとNew-CsMediaConfigurationしてSet-CsMediaConfigurationします。<br/>有効な値は次のとおりです。<br/><br/>**必須**: SRTP 暗号化を使用する必要があります。<br/>**オプション**: ゲートウェイが SRTP をサポートしている場合は SRTP が使用されます。<br/>**サポートされていません**: SRTP 暗号化はサポートされていないので、使用されません。<br/><br/>SRTPMode は、ゲートウェイがトランスポート層セキュリティ (TLS) プロトコルを使用するよう構成されている場合にのみ使用されます。ゲートウェイがトランスポートとして伝送制御プロトコル (TCP) を使用するように構成されている場合は、SRTPMode は内部で Not Supported に設定されます。|
|サポートの参照|Enable3pccRefer<br/>EnableReferSupport|[**ゲートウェイへの参照の送信を有効にする**] に設定した場合、トランクが仲介サーバーからの REFER 要求の受信をサポートすることを示します。<br/>[**サードパーティ通話コントロールを使用する参照を有効にする**] に設定すると、3PCC プロトコルを使用して転送される通話がホストされたサイトをバイパスできるようにすることを示します。3PCC は、「三者間通話コントロール」とも呼ばれ、第三者を使用して二人の通話者を接続するとき (たとえば、オペレーターが人物 A から人物 B への通話を接続するとき) に使用します。|
|メディアのバイパスを有効にする|EnableBypass|メディア バイパスがこのトランクに対して有効かどうかを示します。メディア バイパスは、[**集中メディア処理**] も有効になっている場合にのみ有効にできます。|
|集中メディア処理|PologyTopology|既知のメディア終端ポイントがあるかどうかを示します (既知のメディア終端ポイントの例として、メディア終端が信号終端と同じ IP を持つ PSTN ゲートウェイがあります)。|
|RTP ラッチを有効にする|EnableRTPLatching|SIP トランクが RTP ラッチをサポートするかどうかを示します。RTP ラッチは、NAT (ネットワーク アドレス変換) 装置またはファイアウォールを経由した RTP/RTCP 接続を可能にする技術です。|
|着信転送履歴を有効にする|ForwardCallHistory|通話履歴の情報をトランク経由で転送するかどうかを示します。|
|P-Asserted-Identity データの転送を有効にする|ForwardPAI|P-Asserted-Identity (PAI) ヘッダーを通話とともに転送するかどうかを示します。PAI ヘッダーがあれば、発信者 ID を確認できます。|
|送信ルーティング フェールオーバー タイマーを有効にする|EnableFastFailoverTimer|発信通話が 10 秒以内にゲートウェイによって応答されない場合に次に使用できるトランクにルーティングするかどうかを示します。他にトランクがない場合は、通話は自動的に破棄されます。ネットワークおよびゲートウェイの応答が遅い環境の場合、通話が不必要に破棄されるようになる可能性があります。|
|関連付けられている PSTN 使用法|PSTNUsages|トランクに割り当てられた PSTN 使用法のコレクションです。|
|テストする変換後の番号|N/A|トランクの構成設定の臨時テストを行うために使用できる電話番号です。|
|関連付けられている変換ルール|OutboundTranslationRulesList|発信ルーティングによって処理される通話 (PBX または PSTN の宛先にルーティングされる通話) に適用される、電話番号変換ルールのコレクションです。|
|着信者番号の変換ルール|OutboundCallingNumberTranslationRulesList|トランクに割り当てられた発信電話番号の変換ルールのコレクションです。|
|テストする電話番号|N/A|変換ルールの臨時テストを行うために使用できる電話番号です。|
|発信者番号|N/A|テストする電話番号が発信者の電話番号であることを示します。|
|着信者番号|N/A|テストする電話番号が着信者の電話番号であることを示します。|
|||

> [!Note]
> Skype for Business Server CsTrunkConfiguration コマンドレットは、Skype for Business Server コントロール パネルに表示されない追加のプロパティをサポートします。 詳細については [、Set-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration) コマンドレットのヘルプ トピックを参照してください。 

**Skype for Business Server コントロール パネルを使用して SIP トランク構成設定を変更するには**

1. Skype for Business Server コントロール パネルで、[音声ルーティング] **をクリックし**、[トランク構成] を **クリックします**。
2. [**トランク構成**] タブで、変更するトランク構成の設定をダブルクリックします。編集できる設定のコレクションは一度に 1 つだけです。複数のコレクションで同じ変更を行う場合は、Windows PowerShell を使用してください。
3. [トランク **構成の編集]** ダイアログ ボックスで、適切な選択を行い **、[OK]** をクリックします。
4. コレクションの [状態] プロパティが [コミットされていません] に更新されます。 変更をコミットし、コレクションを削除するには、[コミット]をクリックし、[すべて確定]**をクリックします**。
5. [コミット **されていない音声構成設定]** ダイアログ ボックスで **、[OK]** をクリックします。
6. [Skype **for Business Server コントロール パネル] ダイアログ** ボックスで **、[OK]** をクリックします。
