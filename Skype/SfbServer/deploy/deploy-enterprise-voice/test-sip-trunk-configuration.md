---
title: 'Skype for Business Server: SIP トランク構成設定をテストする'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: '概要: 管理シェルを使用して SIP トランク構成設定をテストするSkype for Business Server説明します。'
ms.openlocfilehash: e6acdc50aaabffabf5b54dd0566143ea0d27d155
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764865"
---
# <a name="skype-for-business-server-test-sip-trunk-configuration-settings"></a>Skype for Business Server: SIP トランク構成設定をテストする
 
**概要:** 管理シェルを使用して SIP トランク構成設定をテストするSkype for Business Server説明します。
  
SIP トランク構成設定は、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ、IP-Public ブランチ eXchange (PBX)、またはサービス プロバイダーのセッション ボーダー コントローラー (SBC) との間の関係と機能を定義します。 たとえば、次の設定ができます。
  
- トランクでメディア バイパスを有効にする必要があるかどうか
    
- リアルタイム トランスポート制御プロトコル (RTCP) パケットが送信される条件
    
- 各トランクで Secure Realtime Transport Protocol (SRTP) 暗号化が必要かどうか
    
サーバーをインストールSkype for Business Server、SIP トランク構成設定のグローバル コレクションが作成されます。 また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定コレクションを作成できます。 管理者は、Test-CsTrunkConfiguration コマンドレットを使用して、トランクがユーザーがダイヤルした番号をゲートウェイが処理できる番号に変換できると確認することもできます。
  
トランク構成設定は、Windows PowerShell と [Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration) コマンドレットを使用する方法でのみテストできます。 このコマンドレットは、管理シェルから、Skype for Business Server管理シェルのリモート セッションSkype for Business Server実行できます。
  
### <a name="to-test-sip-trunk-configuration-settings"></a>SIP トランク構成設定をテストするには

- このコマンドを実行すると、ダイヤルされた番号 4255551212 がレドモンド サイトのトランク構成設定によって正しく変換できることを確認できます。
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```
