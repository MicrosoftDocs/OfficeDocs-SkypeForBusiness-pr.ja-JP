---
title: Skype for Business Server で SIP トランク構成設定をテストする
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
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: '概要: Skype for Business Server 管理シェルを使用して SIP トランク構成設定をテストする方法について説明します。'
ms.openlocfilehash: 6f569c7e397e7902cb347e13b4077acb5a9b34fb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103373"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server で SIP トランク構成設定をテストする
 
**概要:** Skype for Business Server 管理シェルを使用して SIP トランク構成設定をテストする方法について説明します。
  
SIP トランク構成設定は、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ、IP-Public ブランチ eXchange (PBX)、またはサービス プロバイダーのセッション ボーダー コントローラー (SBC) との間の関係と機能を定義します。 たとえば、次の設定ができます。
  
- トランクでメディア バイパスを有効化するか。
    
- リアルタイム トランスポート制御プロトコル (RTCP) パケットが送信される条件。
    
- 各トランクで Secure Realtime Transport Protocol (SRTP) 暗号化が必要かどうか。
    
Skype for Business Server をインストールすると、SIP トランク構成設定のグローバル コレクションが作成されます。 また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。 管理者は、Test-CsTrunkConfiguration コマンドレットを使用して、ユーザーがダイヤルした番号をゲートウェイで処理可能な番号にトランクが変換できるかどうかも確認できます。
  
トランク構成設定は、Windows PowerShell と [Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) コマンドレットを使用する方法でのみテストできます。 このコマンドレットは、Skype for Business Server 管理シェルから、または Skype for Business Server 管理シェルのリモート セッションから実行できます。
  
### <a name="to-test-sip-trunk-configuration-settings"></a>SIP トランク構成設定をテストするには

- このコマンドを実行すると、ダイヤルされた番号 4255551212 がレドモンド サイトのトランク構成設定によって正しく変換できることを確認できます。
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```