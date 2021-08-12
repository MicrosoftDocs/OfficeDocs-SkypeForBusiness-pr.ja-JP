---
title: Skype for Business Server - SIP トランク構成設定のテスト
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
description: 'SIP トランク構成設定は、仲介サーバーと PST) ゲートウェイ、PBX、またはサービス プロバイダーの SBC の間の関係と機能を定義します。 '
ms.openlocfilehash: b6154c1f6a608d0cac0084b3c49caf2b7aa630229464d922926f0eeb4ad20f7f
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848992"
---
# <a name="skype-for-business-server---test-sip-trunk-configuration-settings"></a>Skype for Business Server - SIP トランク構成設定のテスト

SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係および機能を定義します。たとえば、次の設定ができます。

- トランクでメディア バイパスを有効化するか。
- Real-time Transport Control Protocol (RTCP) パケットが送信される条件。
- 各トランクでセキュア リアルタイム プロトコル (SRTP) 暗号化を要求するか。

サーバーをインストールSkype for Business Server、SIP トランク構成設定のグローバル コレクションが作成されます。 また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。 管理者は [、Test-CsTrunkConfiguration](/powershell/module/skype/Test-CsTrunkConfiguration) コマンドレットを使用して、トランクがユーザーがダイヤルした番号をゲートウェイで処理できる番号に変換できる可能性を確認することもできます。

トランク構成設定は、Windows PowerShell と Test-CsTrunkConfiguration コマンドレットを使用する方法でのみテストできます。 このコマンドレットは、管理シェルから、またはSkype for Business Serverのリモート セッションから実行Windows PowerShell。 

**SIP トランク構成設定をテストするには**

このコマンドを実行すると、ダイヤルされた番号 4255551212 がレドモンド サイトのトランク構成設定によって正しく変換できることを確認できます。

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
