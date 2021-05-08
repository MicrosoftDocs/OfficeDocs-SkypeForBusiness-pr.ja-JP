---
title: Skype Room System のドメイン参加に関する考慮事項
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: 管理者は、Skype Room System アプライアンス PC を Active Directory ドメインに参加する方法と、それに関する考慮事項について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c322819fb765e05cead793c95b5e3b6af2d2a180
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117555"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Skype Room System ドメイン参加に関する考慮事項
 
このトピックでは、Skype Room System アプライアンス PC をドメインに参加させる方法について説明します。
  
## <a name="domain-joining-considerations"></a>ドメイン参加に関する考慮事項

Skype Room System アプライアンス PC を Active Directory ドメインに参加させるか、あるいはワークグループに入れたままにしておくことができます。 この決定を行う前に、次の点を考慮してください。
  
- Skype Room System アプライアンス PC をドメインに参加させると、組織のプライベート ルート証明書チェーンの自動インポートが容易になります。
- Skype Room System アプライアンス PC をドメインに参加させると、ドメイン ユーザーとグループに管理者権限を与えることができます。 これにより、ローカル コンピューター レベルの管理者アカウントのパスワードを記憶する必要がなくなります。
- Skype Room System アプライアンス PC をドメインに参加する場合、すべての Skype Room System マシン オブジェクトが存在する OU にグループ ポリシー オブジェクト (GPO) の除外を提供できるよう、個別の組織単位 (OU) を作成する必要があります。 その場合、Skype Room System アプライアンス PC をドメインに参加させる前に OU にマシン オブジェクトを作成します。
- 多くの組織では、次の GPO が用意されています。それらは Skype Room System アプライアンス PC 機能に影響します。 Skype Room System OU でこれらの GPO の継承を上書きするか、ブロックしてください。

  - ログオン セッションのタイムアウト (自動ロックアウト)
  - 電源管理に関連するポリシー
  - 追加の認証手順が必要
  - ローカル ドライブへのアクセスを拒否
  - ユーザーに低速のネットワーク接続を推奨する
  - ログオン時に特定のプログラムを起動する
  - ドメインに参加するすべてのマシンで別のドメイン ユーザー アカウントを作成する。
  - Skype Room System に Windows Update をプッシュする
    
- 代替策として、アプライアンス PC をワークグループに残しておくこともできます。 デスクトップ Microsoft Teams や Skype for Business クライアントの場合と同様に、この操作を行うには Skype Room System アプライアンス PC でルート証明書チェーンを手動でインポートする必要があります。 ただし、展開でパブリック証明書 (たとえば、Entrust、VeriSign など) を使用している場合は、ルート証明書チェーンをインポートする必要はありません。 
    
Skype Room System マシンをドメインに参加させる計画を立てる場合、GPO の範囲外になる可能性があるため、Skype Room System マシンを意図しない OU に誤って参加させないように、正しい OU に参加するようにしてください。 Skype Room System マシンから次のコマンドレットを使用することで、正しい OU に参加させることができ、LRS 機能をブロックする可能性のある GPO を受け取ることはありません。 次のコマンドレットを実行するには、システム管理者または OEM パートナーに問い合わせてください。
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

別の OU を作成し、継承をブロックする場合でも、より高いレベルで問題が発生する可能性があるいくつかのポリシーがあります。 No Override を設定したグループ ポリシーは、Block Policy Inheritance を設定した OU より優先されます。 詳細については、グループ ポリシーの [ドキュメントの「](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) ポリシーの継承をブロックする場合と比較してオーバーライドなし」を参照してください。
  
これらの問題を解決する手段は、1 つではないかもしれません。 適切な GPO 設定を持つ OU、または前に説明したポリシーが存在しない OU が提供される場合は、Active Directory の専門家に相談してください。 ルーム システム デバイスに対してサービス品質 (QoS) Skypeを有効にしてください。

## <a name="related-topics"></a>関連トピック
  
[デバイス構成: 新規作成または現在の形式のままで編集](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[サービスの品質の管理](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)