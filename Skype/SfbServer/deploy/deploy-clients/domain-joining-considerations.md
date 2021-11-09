---
title: SkypeRoom System ドメイン参加に関する考慮事項
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: このトピックでは、Room System アプライアンス PC をドメインにSkypeする方法について説明します。
ms.openlocfilehash: d3c94a4983bddb051bda29badf5c569eeef635a3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844870"
---
# <a name="skype-room-system-domain-joining-considerations"></a>SkypeRoom System ドメイン参加に関する考慮事項
 
このトピックでは、Room System アプライアンス PC をドメインにSkypeする方法について説明します。
  
## <a name="domain-joining-considerations"></a>ドメイン参加に関する考慮事項

ルーム システム アプライアンス PC Skype Active Directory ドメインに参加するか、ワークグループに残します。 この決定を行う前に、次の点を検討してください。
  
- Room System アプライアンス PC Skype参加すると、組織のプライベート ルート証明書チェーンを自動的にインポートできます。
    
- Room System アプライアンス PC Skype参加すると、ドメイン ユーザーとグループの管理者権限を付与できます。 これにより、ローカル コンピューター レベルの管理者アカウントのパスワードを覚えておく必要はありません。
    
- Skype Room System アプライアンス PC をドメインに参加する場合、別の組織単位 (OU) を作成して、すべての Skype Room System マシン オブジェクトが存在する OU にグループ ポリシー オブジェクト (GPO) の除外を提供する必要があります。 これを行う場合は、ルーム システム アプライアンス PC をドメインに参加する前Skype OU にマシン オブジェクトを作成します。
    
- 多くの組織では、Room System アプライアンス PC の機能に影響Skype GPO があります。 ルーム システム OU でこれらの GPO の継承をオーバーライドまたはブロックSkype確認します。 
    
  - ログオン セッションのタイムアウト (自動ロックアウト)
    
  - 電源管理関連のポリシー
    
  - 追加の認証手順を要求する
    
  - ローカル ドライブへのアクセスを拒否する
    
  - 低速のネットワーク接続をユーザーに求める
    
  - ログオン時に特定のプログラムを開始する
    
  - すべてのドメインに参加しているコンピューターに別のドメイン ユーザー アカウントを作成します。
    
  - [更新Windowsルーム システムSkypeプッシュ]
    
- または、アプライアンス PC をワークグループに残す場合があります。 デスクトップ クライアントと同様Skype for Business、ルーム システム アプライアンス PC でルート証明書チェーンを手動Skypeする必要があります。 Skype for Business 展開でパブリック証明書 (Entrust、VeriSign など) を使用している場合は、ルート証明書チェーンをインポートする必要はありません。 
    
Skype Room System マシンをドメインに参加する予定の場合は、Skype Room System マシンが意図しない OU に不注意で参加しないようにしてください。GPO から解放されない可能性があります。正しい OU に参加していることを確認してください。 次のコマンドレットを使用して、Skype Room System マシンから正しい OU に参加し、LRS 機能をブロックする可能性がある GPO を受信することはできません。 次のコマンドレットを実行するには、システム管理者または OEM パートナーに問い合わせてください。
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

別の OU を作成して継承をブロックしても、より高いレベルで問題が発生する可能性があるポリシーもあります。 [上書きなし] 設定のグループ ポリシーは、[ポリシーの継承をブロック] 設定を使用して OU を打ち負かします。 詳細については、「グループ ポリシー」のドキュメントの「 [ポリシー](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) の継承をブロックする」の記事「上書きなし」を参照してください。
  
これらの問題を解決するには、複数の方法があります。 Active Directory の専門家に相談して、適切な GPO 設定を持つ OU、または前に説明したポリシーが存在しない OU が提供されている必要があります。 ルーム システム デバイスに対してサービス品質 (QoS) を有効Skype推奨されます。

## <a name="see-also"></a>関連項目
  
[デバイス構成: 新規作成または現在の形式のままで編集](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[サービス品質の管理](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)