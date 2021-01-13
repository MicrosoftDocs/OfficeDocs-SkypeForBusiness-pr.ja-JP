---
title: Skype Room System のドメイン参加に関する考慮事項
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: このトピックでは、Skype Room System アプライアンス PC をドメインに参加する方法について説明します。
ms.openlocfilehash: 6d6decf689b1a38615851911b42676050a823e4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805917"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Skype Room System のドメイン参加に関する考慮事項
 
このトピックでは、Skype Room System アプライアンス PC をドメインに参加する方法について説明します。
  
## <a name="domain-joining-considerations"></a>ドメイン参加に関する考慮事項

Skype Room System アプライアンス PC を Active Directory ドメインに参加するか、ワークグループに残します。 この決定を行う前に、次の点を考慮してください。
  
- Skype Room System アプライアンス PC のドメイン参加は、組織のプライベート ルート証明書チェーンを自動的にインポートするのに役立ちます。
    
- Skype Room System アプライアンス PC をドメインに参加すると、ドメイン ユーザーとグループに管理者権限を付与できます。 そうすることで、ローカル コンピューター レベルの管理者アカウント パスワードを覚えておく必要はありません。
    
- Skype Room System アプライアンス PC をドメインに参加する場合、すべての Skype Room System コンピューター オブジェクトが存在する OU にグループ ポリシー オブジェクト (GPO) の除外を提供できるよう、個別の組織単位 (OU) を作成する必要があります。 これを行う場合は、Skype Room System アプライアンス PC をドメインに参加する前に OU にマシン オブジェクトを作成します。
    
- 多くの組織には、Skype Room System アプライアンス PC の機能に影響する次の GPO があります。 Skype Room System OU でこれらの GPO の継承を上書きまたはブロックします。 
    
  - ログオン セッションのタイムアウト (自動ロックアウト)
    
  - 電源管理に関連するポリシー
    
  - 追加の認証手順を要求する
    
  - ローカル ドライブへのアクセスを拒否する
    
  - 低速なネットワーク接続をユーザーに求める
    
  - ログオン時に特定のプログラムを開始する
    
  - ドメインに参加しているすべてのコンピューターに別のドメイン ユーザー アカウントを作成します。
    
  - Skype Room System への Windows Update のプッシュ
    
- または、アプライアンス PC をワークグループに残しておく場合があります。 デスクトップの Skype for Business クライアントと同様に、Skype Room System アプライアンス PC にルート証明書チェーンを手動でインポートする必要があります。 Skype for Business 展開でパブリック証明書 (たとえば、Entrust、VeriSign など) を使用している場合は、ルート証明書チェーンをインポートする必要はありません。 
    
Skype Room System コンピューターをドメインに参加する予定の場合は、SKYPE Room System コンピューターが意図しない OU に誤って参加しないようにしてください。GPO から解放されない可能性があります。正しい OU に参加していることを確認してください。 Skype Room System コンピューターから次のコマンドレットを使用して正しい OU に参加できます。また、LRS 機能をブロックする可能性がある GPO を受信することはできません。 次のコマンドレットを実行するには、システム管理者または OEM パートナーに問い合わせてください。
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

別の OU を作成して継承をブロックする場合でも、より高いレベルで問題を引き起こす可能性があるいくつかのポリシーがあります。 [上書きなし] 設定を持つグループ ポリシーは、ポリシーの継承をブロックする設定を持つ OU より優先されます。 詳細については、「グループ ポリシー」のドキュメントの記事 [「No Override as Compared to Block Policy Inheritance」](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) を参照してください。
  
これらの問題を解決するには、複数の方法があります。 Active Directory の専門家に相談して、適切な GPO 設定を持つ OU、または前に説明したポリシーが存在しない OU を必ず提供するようにお願いします。 Skype Room System デバイスのサービス品質 (QoS) を有効にしてください。

## <a name="see-also"></a>関連項目
  
[デバイス構成: 新規作成または現在の形式のままで編集](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[サービスの品質の管理](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
