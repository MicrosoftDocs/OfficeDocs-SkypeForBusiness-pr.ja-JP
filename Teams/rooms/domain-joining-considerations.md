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
description: このトピックでは、Skype Room System アプライアンス PC をドメインに参加させる方法について説明します。
ms.openlocfilehash: f2cad169b812d3da3a964c96adabc498df1009b8
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826085"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Skype Room System ドメイン参加に関する考慮事項
 
このトピックでは、Skype Room System アプライアンス PC をドメインに参加させる方法について説明します。
  
## <a name="domain-joining-considerations"></a>ドメイン参加に関する考慮事項

Skype Room System アプライアンス PC を Active Directory ドメインに参加させるか、あるいはワークグループに入れたままにしておくことができます。 この決定を行う前に、次の点を考慮してください。
  
- Skype Room System アプライアンス PC をドメインに参加させると、組織のプライベート ルート証明書チェーンの自動インポートが容易になります。
- Skype Room System アプライアンス PC をドメインに参加させると、ドメイン ユーザーとグループに管理者権限を与えることができます。 これにより、ローカル コンピューター レベルの管理者アカウントのパスワードを記憶する必要がなくなります。
- Skype Room System アプライアンス PC をドメインに参加させる場合、グループ ポリシー オブジェクト (GPO) の例外を、すべての Skype Room System マシン オブジェクトが配置されている OU に提供できるよう、独立した組織単位 (OU) を作成する必要があります。 その場合、Skype Room System アプライアンス PC をドメインに参加させる前に OU にマシン オブジェクトを作成します。
- 多くの組織では、次の GPO が用意されています。それらは Skype Room System アプライアンス PC 機能に影響します。 Skype Room System OU でこれらの GPO の継承を上書きするか、ブロックしてください。

  - ログオン セッションのタイムアウト (自動ロックアウト)
  - 電源管理関連のポリシー
  - 追加の認証手順が必要
  - ローカル ドライブへのアクセスを拒否
  - ユーザーに低速のネットワーク接続を推奨する
  - ログオン時に特定のプログラムを起動する
  - ドメインに参加するすべてのマシンで別のドメイン ユーザー アカウントを作成する。
  - Skype Room System に Windows Update をプッシュする
    
- 代替策として、アプライアンス PC をワークグループに残しておくこともできます。 デスクトップ Microsoft Teams や Skype for Business クライアントの場合と同様に、この操作を行うには Skype Room System アプライアンス PC でルート証明書チェーンを手動でインポートする必要があります。 ただし、展開でパブリック証明書 (たとえば、Entrust、VeriSign など) を使用している場合は、ルート証明書チェーンをインポートする必要はありません。 
    
Skype Room System マシンをドメインに参加させる計画を立てる場合、GPO の範囲外になる可能性があるため、Skype Room System マシンを意図しない OU に誤って参加させないように、正しい OU に参加するようにしてください。 Skype Room System マシンから次のコマンドレットを使用することで、正しい OU に参加させることができ、LRS 機能をブロックする可能性のある GPO を受け取ることはありません。 これらのコマンドレットを実行するには、システム管理者か OEM パートナーに連絡してください。
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

独立した OU を作成して継承をブロックしても、ハイ レベルな部分で問題を引き起こす可能性のあるポリシーがいくつか存在します。 No Override を設定したグループ ポリシーは、Block Policy Inheritance を設定した OU より優先されます。 詳細については、グループ ポリシーに関するドキュメントの「[No Override と Block Policy Inheritance の比較](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10))」を参照してください。
  
これらの問題を解決する手段は、1 つではないかもしれません。 組織の Active Directory の専門家に、適切な GPO 設定の OU、少なくとも上で説明したポリシーが存在しない OU が提供されていることを確認するようにしてください。 また、Skype Room System デバイスでサービスの品質 (QoS) を有効にしておくことを推奨します。

## <a name="see-also"></a>関連項目
  
[デバイス構成: 新規作成または現在の形式のままで編集](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[サービスの品質の管理](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
