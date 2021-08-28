---
title: 外部ユーザーのフェデレーションとリモート アクセスの確認
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: フェデレーション ルートを Skype for Business Server 2019 エッジ サーバーに移行した後、いくつかの機能テストを実行して、フェデレーションが期待通り実行されるのを確認する必要があります。 外部ユーザー アクセスのテストには、次のいずれかまたはすべてなど、組織がサポートしている各種類の外部ユーザーを含める必要があります。
ms.openlocfilehash: ef6e41242462f218ab96db94dd8a2b5df1b388bb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592961"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>外部ユーザーのフェデレーションとリモート アクセスの確認

フェデレーション ルートを Skype for Business Server 2019 エッジ サーバーに移行した後、いくつかの機能テストを実行して、フェデレーションが期待通り実行されるのを確認する必要があります。 外部ユーザー アクセスのテストには、次のいずれかまたはすべてなど、組織がサポートしている各種類の外部ユーザーを含める必要があります。
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>外部ユーザーの接続と外部アクセスのテスト

- 少なくとも 1 Skype for Business Server つのフェデレーション ドメイン、2019 年 2019 年の内部ユーザー、およびレガシ インストールのユーザー。 インスタント メッセージング (IM)、プレゼンス、音声ビデオ (A/V)、およびデスクトップ共有をテストします。
    
- Skype for Business Server 2019 のユーザーと従来のインストールのユーザーとの通信を組織がサポートする (およびプロビジョニングが完了した) 各パブリック IM サービス プロバイダーのユーザー。 
    
- 匿名ユーザーが会議に参加できることを確認します。
    
- Skype for Business Server 2019 のユーザー、およびレガシ インストールのユーザーとのリモート ユーザー アクセス (イントラネット外からログ i nto Lync Server/Skype for Business を VPN なし) を使用してレガシ インストールでホストされているユーザー。 IM、プレゼンス、A/V、およびデスクトップ共有をテストします。
    
- Skype for Business Server 2019 でユーザーがリモート ユーザー アクセス (イントラネットの外部から Skype for Business Server 2019 にログインするが VPN なし) を使用して Skype for Business Server 2019 でホストされたユーザーと、レガシ インストールのユーザー。 IM、プレゼンス、A/V、およびデスクトップ共有をテストします。
    

