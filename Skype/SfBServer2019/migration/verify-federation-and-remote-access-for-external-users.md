---
title: 外部ユーザーのフェデレーションとリモート アクセスの確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス 2019 エッジ サーバーのフェデレーション ルート、Skype を移行した後は、フェデレーションが期待どおりに実行されることを確認するのにはいくつかの機能テストを行う必要があります。 外部ユーザー アクセスのテストには、次の一部またはすべてを含む、組織をサポートする外部ユーザーの種類を含める必要があります。
ms.openlocfilehash: 3a520b39d76ab93f4ec7fcaacd139b3f83a3326a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231351"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>外部ユーザーのフェデレーションとリモート アクセスの確認

ビジネス 2019 エッジ サーバーのフェデレーション ルート、Skype を移行した後は、フェデレーションが期待どおりに実行されることを確認するのにはいくつかの機能テストを行う必要があります。 外部ユーザー アクセスのテストには、次の一部またはすべてを含む、組織をサポートする外部ユーザーの種類を含める必要があります。
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>外部のユーザーと外部アクセスの接続をテストします。

- 少なくとも 1 つのフェデレーション ドメイン、内部のビジネス サーバー 2019、Skype のユーザーと従来のユーザーからのユーザーをインストールします。 インスタント メッセージング (IM)、プレゼンス、オーディオとビデオをテストする (A/V)、デスクトップの共有とします。
    
- 組織をサポートするなど準備が完了した対象の各パブリック IM サービス プロバイダーのユーザー ビジネス サーバー 2019 および従来のインストール時にユーザーの Skype 上のユーザーと通信します。 
    
- 匿名ユーザーが会議に参加することであることを確認します。
    
- 従来でホストされているユーザーは、リモート ユーザー アクセスを使用してをインストール (i のログ %ndns Lync Server と Skype からビジネスの VPN のせずにイントラネットの外部) のビジネス サーバー 2019、Skype のユーザーと従来のインストール時にユーザーにします。 テスト IM、プレゼンス、A/V、およびデスクトップの共有します。
    
- ビジネス サーバー 2019、Skype のユーザーと従来のユーザーとリモート ユーザー アクセス (ログ Skype にからのビジネス サーバー 2019 の VPN のせずにイントラネットの外部) を使用して、ビジネス サーバー 2019 の Skype 上でホストされているユーザーをインストールします。 テスト IM、プレゼンス、A/V、およびデスクトップの共有します。
    

