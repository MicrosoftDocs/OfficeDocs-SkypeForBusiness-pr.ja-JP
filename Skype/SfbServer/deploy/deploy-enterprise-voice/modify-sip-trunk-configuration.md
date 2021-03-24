---
title: Skype for Business Server での SIP トランク構成設定の変更
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
description: '概要: Skype for Business Server コントロール パネルを使用して SIP トランク構成設定を変更する方法について説明します。'
ms.openlocfilehash: 34db4126f8f91ecfd7d68f0f982be5c81769b455
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103419"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server での SIP トランク構成設定の変更
 
**概要:** Skype for Business Server コントロール パネルを使用して SIP トランク構成設定を変更する方法について説明します。
  
SIP トランク構成設定は、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ、IP-Public Branch eXchange (PBX)、またはサービス プロバイダーのセッション ボーダー コントローラー (SBC) との間の関係と機能を定義します。 たとえば、次の設定ができます。
  
- トランクでメディア バイパスを有効化するか。
    
- リアルタイム トランスポート制御プロトコル (RTCP) パケットが送信される条件。
    
- 各トランクで Secure Realtime Transport Protocol (SRTP) 暗号化が必要かどうか。
    
Skype for Business Server をインストールすると、SIP トランク構成設定のグローバル コレクションが作成されます。 また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。 これらのコレクションは、後で Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して変更できます。
  
Skype for Business Server コントロール パネルを使用して SIP トランク構成設定を変更する場合は、次のオプションを使用できます。
  
|**UI 設定**|**PowerShell パラメーター**|**説明**|
|:-----|:-----|:-----|
|名前  <br/> |ID  <br/> |コレクションの一意の識別子。このプロパティは読み取り専用です。トランク構成設定のコレクションの Identity は変更できません。  <br/> |
|説明  <br/> |説明  <br/> |管理者が、設定に関する追加情報を格納できます (たとえば、トランク構成の目的)。  <br/> |
|サポートされる最大初期ダイアログの数  <br/> |MaxEarlyDialogs  <br/> |サービス プロバイダーの PSTN ゲートウェイ、IP-PBX、または SBC が、仲介サーバーに送信した INVITE に対して受信できる分岐応答の最大数です。  <br/> |
|暗号化サポート レベル  <br/> |SRTPMode  <br/> | 仲介サーバーと、サービス プロバイダーの PSTN ゲートウェイ、IP-PBX、または SBC 間のメディア トラフィックを保護するためのサポート レベルを示します。 メディア バイパスの場合、この値はメディア構成の EncryptionLevel 設定と互換性を持つ必要があります。 メディア構成は [、New-CsMediaConfiguration](/powershell/module/skype/new-csmediaconfiguration?view=skype-ps) コマンドレットと [Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps) コマンドレットを使用して設定されます。 <br/>  有効な値は次のとおりです。 <br/>  Required: SRTP 暗号化を使用する必要があります。 <br/>  Optional: ゲートウェイでサポートされている場合は、SRTP が使用されます。 <br/>  Not Supported: SRTP 暗号化がサポートされていないので、使用されません。 <br/>  SRTPMode は、ゲートウェイがトランスポート層セキュリティ (TLS) プロトコルを使用するよう構成されている場合にのみ使用されます。ゲートウェイがトランスポートとして伝送制御プロトコル (TCP) を使用するように構成されている場合は、SRTPMode は内部で Not Supported に設定されます。<br/> |
|サポートの参照  <br/> |Enable3pccRefer  <br/> EnableReferSupport  <br/> |[**ゲートウェイへの参照の送信を有効にする**] に設定した場合、トランクが仲介サーバーからの REFER 要求の受信をサポートすることを示します。  <br/> [**サードパーティ通話コントロールを使用する参照を有効にする**] に設定すると、3PCC プロトコルを使用して転送される通話がホストされたサイトをバイパスできるようにすることを示します。3PCC は、「三者間通話コントロール」とも呼ばれ、第三者を使用して二人の通話者を接続するとき (たとえば、オペレーターが人物 A から人物 B への通話を接続するとき) に使用します。<br/> |
|メディアのバイパスを有効にする  <br/> |EnableBypass  <br/> |メディア バイパスがこのトランクに対して有効かどうかを示します。メディア バイパスは、[**集中メディア処理**] も有効になっている場合にのみ有効にできます。<br/> |
|集中メディア処理  <br/> |ConcentratedTopology  <br/> |既知のメディア終端ポイントがあるかどうかを示します (既知のメディア終端ポイントの例として、メディア終端が信号終端と同じ IP を持つ PSTN ゲートウェイがあります)。  <br/> |
|RTP ラッチを有効にする  <br/> |EnableRTPLatching  <br/> |SIP トランクが RTP ラッチをサポートするかどうかを示します。RTP ラッチは、NAT (ネットワーク アドレス変換) 装置またはファイアウォールを経由した RTP/RTCP 接続を可能にする技術です。  <br/> |
|着信転送履歴を有効にする  <br/> |ForwardCallHistory  <br/> |通話履歴の情報をトランク経由で転送するかどうかを示します。  <br/> |
|P-Asserted-Identity データの転送を有効にする  <br/> |ForwardPAI  <br/> |P-Asserted-Identity (PAI) ヘッダーを通話とともに転送するかどうかを示します。PAI ヘッダーがあれば、発信者 ID を確認できます。  <br/> |
|送信ルーティング フェールオーバー タイマーを有効にする  <br/> |EnableFastFailoverTimer  <br/> |発信通話が 10 秒以内にゲートウェイによって応答されない場合に次に使用できるトランクにルーティングするかどうかを示します。他にトランクがない場合は、通話は自動的に破棄されます。ネットワークおよびゲートウェイの応答が遅い環境の場合、通話が不必要に破棄されるようになる可能性があります。  <br/> |
|関連付けられている PSTN 使用法  <br/> |PSTNUsages  <br/> |トランクに割り当てられた PSTN 使用法のコレクションです。  <br/> |
|テストする変換後の番号  <br/> |該当なし  <br/> |トランクの構成設定の臨時テストを行うために使用できる電話番号です。  <br/> |
|関連付けられている変換ルール  <br/> |OutboundTranslationRulesList  <br/> |発信ルーティングによって処理される通話 (PBX または PSTN の宛先にルーティングされる通話) に適用される、電話番号変換ルールのコレクションです。  <br/> |
|着信者番号の変換ルール  <br/> |OutboundCallingNumberTranslationRulesList  <br/> |トランクに割り当てられた発信電話番号の変換ルールのコレクションです。  <br/> |
|テストする電話番号  <br/> |該当なし  <br/> |変換ルールの臨時テストを行うために使用できる電話番号です。  <br/> |
|発信者番号  <br/> |該当なし  <br/> |テストする電話番号が発信者の電話番号であることを示します。  <br/> |
|着信者番号  <br/> |該当なし  <br/> |テストする電話番号が着信者の電話番号であることを示します。  <br/> |
   
> [!NOTE]
> Lync Server CsTrunkConfiguration コマンドレットは、Lync Server コントロール パネルに表示されない追加のプロパティをサポートします。 詳細については [、Set-CsTrunkConfiguration](/powershell/module/skype/set-cstrunkconfiguration?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。
  
### <a name="to-modify-sip-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して SIP トランク構成設定を変更するには

1. Skype for Business Server コントロール パネルで、[音声ルーティング] **を** クリックし、[トランク構成] **をクリックします**。
    
2. [**トランク構成**] タブで、変更するトランク構成の設定をダブルクリックします。編集できる設定のコレクションは一度に 1 つだけです。複数のコレクションで同じ変更を行う場合は、Windows PowerShell を使用してください。
    
3. [トランク構成 **の編集] ダイアログ** で、適切な選択を行い **、[OK] をクリックします**。
    
4. コレクションの [**状態**] プロパティが [**コミットされていません**] に更新されます。変更をコミットし、コレクションを削除するには、[**コミット**]、[**すべてコミット**] の順にクリックします。
    
5. [**コミットされていない音声構成設定**] ダイアログ ボックスで、[**OK**] をクリックします。
    
6. [Skype **for Business Server コントロール パネル] ダイアログ ボックスで****、[OK] をクリックします**。
