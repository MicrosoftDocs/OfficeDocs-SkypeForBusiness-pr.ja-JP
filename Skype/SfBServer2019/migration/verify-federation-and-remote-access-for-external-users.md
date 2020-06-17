---
title: 外部ユーザーのフェデレーションとリモート アクセスを確認する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: フェデレーションルートを Skype for Business Server 2019 エッジサーバーに移行した後、機能テストを実行して、フェデレーションが期待どおりに動作することを確認する必要があります。 外部ユーザー アクセスのテストには、次のいずれかまたはすべてなど、組織がサポートしている各種類の外部ユーザーを含める必要があります。
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751669"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>外部ユーザーのフェデレーションとリモート アクセスを確認する

フェデレーションルートを Skype for Business Server 2019 エッジサーバーに移行した後、機能テストを実行して、フェデレーションが期待どおりに動作することを確認する必要があります。 外部ユーザー アクセスのテストには、次のいずれかまたはすべてなど、組織がサポートしている各種類の外部ユーザーを含める必要があります。
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>外部ユーザーの接続と外部アクセスをテストする

- 少なくとも1つのフェデレーションドメイン、Skype for Business Server 2019 上の内部ユーザー、および従来のインストールのユーザー。 インスタント メッセージング (IM)、プレゼンス、音声ビデオ (A/V)、およびデスクトップ共有をテストします。
    
- 組織がサポート (およびプロビジョニングが完了) している各パブリック IM サービスプロバイダーのユーザーは、Skype for Business Server 2019 上のユーザーと従来のインストールのユーザーと通信します。 
    
- 匿名ユーザーが会議に参加できることを確認します。
    
- 従来のインストールで、リモートユーザーアクセス (Lync Server/Skype for Business の外部から VPN を使用しない) を使用してホストされているユーザーが、Skype for Business Server 2019 上のユーザーと、レガシインストール上のユーザーを使用しています。 IM、プレゼンス、A/V、およびデスクトップ共有をテストします。
    
- Skype for business Server 2019 でホストされているユーザー (リモートユーザーアクセスを使用) (skype for business Server 2019 から VPN を使用しない)、Skype for Business Server 2019 のユーザー、およびレガシインストールのユーザーに対してログインします。 IM、プレゼンス、A/V、およびデスクトップ共有をテストします。
    

