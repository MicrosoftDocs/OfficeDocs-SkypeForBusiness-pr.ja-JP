---
title: 外部ユーザーのフェデレーションとリモート アクセスの確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 2019 エッジサーバーへのフェデレーションルートの移行が完了したら、いくつかの機能テストを実行して、フェデレーションが期待どおりに実行されることを確認する必要があります。 外部ユーザーアクセスのテストには、次のいずれか、またはすべてを含む、組織がサポートしている各種類の外部ユーザーを含める必要があります。
ms.openlocfilehash: 7f27fa853c8af2ba5e97835ad1e0dd893c9128e0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812685"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>外部ユーザーのフェデレーションとリモート アクセスの確認

Skype for Business Server 2019 エッジサーバーへのフェデレーションルートの移行が完了したら、いくつかの機能テストを実行して、フェデレーションが期待どおりに実行されることを確認する必要があります。 外部ユーザーアクセスのテストには、次のいずれか、またはすべてを含む、組織がサポートしている各種類の外部ユーザーを含める必要があります。
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>外部ユーザーと外部アクセスの接続性をテストする

- 少なくとも1つのフェデレーションドメイン、Skype for Business Server 2019 の内部ユーザー、レガシインストールのユーザー。 インスタントメッセージング (IM)、プレゼンス、音声/ビデオ (A/V)、デスクトップ共有をテストします。
    
- 組織がサポートしている各パブリック IM サービスプロバイダー (およびプロビジョニングが完了した状態) のユーザーは、Skype for Business Server 2019 およびレガシインストールのユーザーとの通信を行います。 
    
- 匿名ユーザーが会議に参加できることを確認します。
    
- リモートユーザーアクセスを使用してホストされている (Lync Server/Skype for Business を、イントラネットの外部から、VPN を使わずに)、レガシインストールのユーザー2019に対してホストされているユーザー。 IM、プレゼンス、A/V、およびデスクトップ共有をテストします。
    
- Skype for Business server 2019 でホストされているユーザー (リモートユーザーアクセスを使っていますが、skype for business server 2019 のユーザーと、レガシインストールのユーザーによる VPN 2019 を使用していない場合)。 IM、プレゼンス、A/V、およびデスクトップ共有をテストします。
    

