---
title: Skype for Business Server でのエッジ展開の検証
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: '概要: エッジ サーバーまたはエッジ サーバー プールの展開が Skype for Business Server で動作しているのを確認する方法について説明します。'
ms.openlocfilehash: 1da2bed1bc9df7cb118d47c2b27e190546838e1b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804357"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Skype for Business Server でのエッジ展開の検証
 
**概要:** エッジ サーバーまたはエッジ サーバー プールの展開が Skype for Business Server で動作しているのを確認する方法について説明します。
  
エッジ サーバーまたはエッジ サーバー プールを展開したら、正常に動作しているかどうか確認する必要があります。 ここでは、エッジ環境が内部サーバーに接続されていることを確認するのに役立ついくつかの情報と、外部ユーザーがエッジを介して Skype for Business Server 環境に接続できる方法を示します。
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>内部サーバーとエッジ サーバー間の接続を確認する

エッジ サーバーがインストールされている場合は、エッジ サーバーまたはエッジ サーバー プールで接続の検証が自動的に行われますが、この確認は Windows PowerShell。 Get-CsManagementStoreReplicationStatus 中央管理ストアを持つ内部サーバー、または Skype for Business Server コア コンポーネント (OcsCore.msi) がインストールされているドメインに参加しているコンピューターで、OcsCore.msi コマンドレットを実行します。
  
このコマンドを実行した最初の結果では、レプリケーションに対して True ではなく False 状態が返される場合があります。 その場合は、次のコマンドレットInvoke-CsManagementStoreReplicationします。 レプリケーションを完了してから、このコマンドレットを再度実行Get-CsManagementStoreReplicationStatusします。
  
## <a name="verify-connectivity-for-your-external-users"></a>外部ユーザーの接続を確認する

エッジ サーバーの構成を確認し、エッジ サーバーのシナリオに合った適切なメッセージを接続、送信、受信する機能を確認するための最適なツールがあります。 リモート接続テスト [サイトです](https://testconnectivity.microsoft.com/)。 これは、Microsoft サポートによって管理および管理されているサイトです。 このツールを使用するには、Web サイトを参照し、指示に従って適切なシナリオを選択します。
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>外部ユーザー接続をテストする際の考慮すべき点

外部ユーザー アクセスのテストには、組織がサポートする各種類の内部ユーザーを含める必要があります。内部ユーザーには、次の一部またはすべてが含まれます。
  
- 少なくとも 1 つのフェデレーション ドメインのユーザー (すべてテストすることをお勧めします)。
    
- 匿名ユーザー。
    
- 組織内で、リモートで Skype for Business にログインしているが、VPN を使用していないユーザー。
    
これらのテストによって、エッジ サーバーが次のかどうかが判断されます。
  
- ネットワーク外から telnet クライアントを使用して必要なポートをリッスンする。
    
  - 例: telnet sip.contoso.com 443
    
  - 展開に応じて、エッジ サーバーまたはエッジ サーバー プールで使用しているポートで、前のテストを実行する必要があります。
    
- 正確な外部 DNS 解決を実行する。
    
  - ネットワークの外部から、エッジ サーバーまたはエッジ サーバー プールの各外部 FQDN に ping を実行します。 ping が失敗した場合でも、IP アドレスが表示され、以前に割り当てた IP アドレスを比較できます。
    

