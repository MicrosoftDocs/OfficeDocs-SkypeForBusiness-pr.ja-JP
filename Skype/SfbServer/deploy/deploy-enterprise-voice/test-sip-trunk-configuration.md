---
title: Skype のビジネス サーバーの SIP トランクの構成設定をテストします。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: '概要: ビジネス サーバー管理シェルには、Skype を使用して、SIP トランクの構成設定をテストする方法を説明します。'
ms.openlocfilehash: f6a7cfae4a5591fa9325e7b9ac99f4c2b18ed516
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883634"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Skype のビジネス サーバーの SIP トランクの構成設定をテストします。
 
**の概要:** ビジネス サーバー管理シェルには、Skype を使用して、SIP トランクの構成設定をテストする方法について説明します。
  
SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch eXchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係と機能を定義します。たとえば、次の設定ができます。
  
- トランクでメディア バイパスを有効化するか。
    
- Realtime Transport Control Protocol (RTCP) パケットが送信される条件。
    
- 各トランクで Secure Realtime Transport Protocol (SRTP) 暗号化を要求するか。
    
ビジネス サーバーの Skype をインストールすると SIP トランク構成設定のグローバル コレクションが作成されます。 また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。 管理者は、Test-CsTrunkConfiguration コマンドレットを使用して、ユーザーがダイヤルした番号をゲートウェイで処理可能な番号にトランクが変換できるかどうかも確認できます。
  
トランク構成設定をテストするには、Windows PowerShell と[テスト CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps)コマンドレットを使用しています。 ビジネス サーバー管理シェルの Skype または Skype ビジネス サーバー管理シェルのリモート セッションからは、このコマンドレットを実行できます。
  
### <a name="to-test-sip-trunk-configuration-settings"></a>SIP トランク構成設定をテストするには

- このコマンドを実行すると、ダイヤルされた番号 4255551212 がレドモンド サイトのトランク構成設定によって正しく変換できることを確認できます。
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


