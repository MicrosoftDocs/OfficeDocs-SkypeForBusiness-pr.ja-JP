---
title: Skype Room System のドメイン参加に関する考慮事項
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: このトピックでは、Skype Room System アプライアンス PC をドメインに参加させる方法について説明します。
ms.openlocfilehash: 93aa983080ee93f38143224b6c74bdcd6490842c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-domain-joining-considerations"></a>Skype Room System のドメイン参加に関する考慮事項
 
このトピックでは、Skype Room System アプライアンス PC をドメインに参加させる方法について説明します。
  
## <a name="domain-joining-considerations"></a>ドメイン参加に関する考慮事項

PC Skype ルーム システムのアプライアンスを Active Directory ドメインに参加するか、ワークグループ内のままにできます。 決定の前に以下の点を検討してください。
  
- Skype ルーム システム アプライアンス PC のドメイン参加は、組織の秘密のルート証明書チェーンを自動的にインポートするのに役立ちます。
    
- Skype ルーム システム アプライアンス PC のドメイン参加を使用すると、ドメイン ユーザーおよびグループの管理権限を付与します。 そうすることで、ローカル マシン レベルの管理者アカウントのパスワードを覚えておく必要がなくなります。
    
- Skype ルーム システム アプライアンス コンピューターをドメインに参加するときは、必要な Skype ルーム システムのすべてのコンピューター オブジェクトが存在する OU にグループ ポリシー オブジェクト (GPO) の除外を提供できるように、独立した組織単位 (OU) を作成することです。 これを行うと、コンピューター オブジェクトを OU に含まれる Skype ルーム システム アプライアンス PC をドメインに参加する前に作成します。
    
- 多くの組織では、次の Gpo は、Skype ルーム システム アプライアンス PC の機能に影響を与えるがあります。 オーバーライドしたり、Skype ルーム システムの OU で Gpo の継承をブロックすることを確認します。 
    
  - ログオン セッションのタイムアウト (自動ロックアウト)
    
  - 電源管理関連のポリシー
    
  - 追加の認証手順が必要
    
  - ローカル ドライブへのアクセスを拒否
    
  - ユーザーに低速のネットワーク接続を推奨する
    
  - ログオン時に特定のプログラムを起動する
    
  - ドメインに参加するすべてのマシンで別のドメイン ユーザー アカウントを作成する。
    
  - Skype ルーム システムに Windows の更新プログラムをプッシュします。
    
- または、アプライアンス PC をワークグループに残しておくことも可能です。 として Skype ビジネスのクライアントのデスクトップにこの必要があります Skype ルーム システム アプライアンス PC のルート証明書チェーンを手動でインポートするのには。 ビジネス展開するため、Skype が (たとえばと Entrust、VeriSign) のパブリック証明書を使用する場合は、ルート証明書チェーンをインポートする必要がありません。 
    
Skype ルーム システムのコンピューターをドメインに参加する場合は、OU、Gpo からできない可能性があります、意図しないに誤って Skype ルーム システムのマシンへの参加を回避するようにしてください正しい OU に参加します。 Skype ルーム システムのコンピューターから次のコマンドレットを使用して正しい OU に参加することができ、LRS の機能を妨げる可能性がある Gpo を受け取りません。 これらのコマンドレットを実行するには、システム管理者か OEM パートナーに連絡してください。
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"

```

独立した OU を作成して継承をブロックしても、ハイ レベルな部分で問題を引き起こす可能性のあるポリシーがいくつか存在します。 No Override を設定したグループ ポリシーは、Block Policy Inheritance を設定した OU より優先されます。 詳細についてを参照してください「いいえオーバーライドとの比較にポリシーを継承」の記事でグループ ポリシーのドキュメントでhttp://technet.microsoft.com/en-us/library/cc978255.aspxです。
  
これらの問題を解決する手段は、1 つではないかもしれません。 組織の Active Directory の専門家に、適切な GPO 設定の OU、少なくとも上で説明したポリシーが存在しない OU が提供されていることを確認するようにしてください。 Skype ルーム システムのサービス品質 (QoS) を有効にすることをお勧めします。
  

