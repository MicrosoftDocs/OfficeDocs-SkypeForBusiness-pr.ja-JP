---
title: Skype Room System のドメイン参加に関する考慮事項
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: このトピックでは、Skype Room System アプライアンス PC をドメインに参加させる方法について説明します。
ms.openlocfilehash: 934b39a0375085e9b8c18022a4526c76a970aca9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293614"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Skype Room System のドメイン参加に関する考慮事項
 
このトピックでは、Skype Room System アプライアンス PC をドメインに参加させる方法について説明します。
  
## <a name="domain-joining-considerations"></a>ドメイン参加に関する考慮事項

Skype Room System アプライアンス PC には、Active Directory ドメインに参加することも、ワークグループ内に残しておくこともできます。 決定の前に以下の点を検討してください。
  
- ドメイン-Skype Room System アプライアンス PC に参加すると、組織のプライベートルート証明書チェーンを自動的にインポートできます。
    
- ドメイン-Skype Room System アプライアンス PC に参加すると、ドメインユーザとグループの管理権限を付与することができます。 そうすることで、ローカル マシン レベルの管理者アカウントのパスワードを覚えておく必要がなくなります。
    
- Skype Room System アプライアンス PC をドメインに参加させるには、別の組織単位 (OU) を作成する必要があります。これにより、すべての Skype Room System machine オブジェクトが存在する OU にグループポリシーオブジェクト (GPO) の除外が提供されます。 この操作を行う場合は、Skype Room System アプライアンス PC をドメインに参加させる前に、OU にマシンオブジェクトを作成します。
    
- 多くの組織には、次のような Gpo があります。 Skype Room System appliance PC の機能に影響します。 Skype Room System OU でこれらの Gpo の継承を上書きまたはブロックします。 
    
  - ログオン セッションのタイムアウト (自動ロックアウト)
    
  - 電源管理関連のポリシー
    
  - 追加の認証手順が必要
    
  - ローカル ドライブへのアクセスを拒否
    
  - ユーザーに低速のネットワーク接続を推奨する
    
  - ログオン時に特定のプログラムを起動する
    
  - ドメインに参加するすべてのマシンで別のドメイン ユーザー アカウントを作成する。
    
  - Skype Room System に Windows Update をプッシュする
    
- または、アプライアンス PC をワークグループに残しておくことも可能です。 デスクトップ Skype for Business クライアントの場合と同様に、Skype Room System アプライアンス PC にルート証明書チェーンを手動でインポートする必要があります。 Skype for Business の展開で公開証明書 (Entrust、VeriSign など) が使用されている場合は、ルート証明書チェーンをインポートする必要はありません。 
    
Skype Room システムマシンをドメインに参加させることを計画している場合、Skype Room System machine を意図しない OU に参加させないようにしてください。これは、Gpo から無料ではない可能性がありますので、正しい OU に参加してください。 Skype Room System コンピューターの次のコマンドレットを使用して、適切な OU に参加し、LRS 機能をブロックしている可能性のある Gpo を受信することはできません。 これらのコマンドレットを実行するには、システム管理者か OEM パートナーに連絡してください。
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

独立した OU を作成して継承をブロックしても、ハイ レベルな部分で問題を引き起こす可能性のあるポリシーがいくつか存在します。 No Override を設定したグループ ポリシーは、Block Policy Inheritance を設定した OU より優先されます。 詳細については、「グループポリシードキュメントの[ポリシーの継承をブロックする」という](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10))記事を参照してください。
  
これらの問題を解決する手段は、1 つではないかもしれません。 組織の Active Directory の専門家に、適切な GPO 設定の OU、少なくとも上で説明したポリシーが存在しない OU が提供されていることを確認するようにしてください。 Skype Room システムデバイスのサービス品質 (QoS) を有効にすることをお勧めします。

## <a name="see-also"></a>関連項目
  
[デバイス構成: 新規作成または現在の形式のままで編集](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[サービスの品質の管理](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
