---
title: エッジの展開を検証Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: '概要: エッジ サーバーまたはエッジ サーバー プールの展開が、エッジ サーバー プールで動作Skype for Business Server。'
ms.openlocfilehash: 175baab9770e6013820e0e632712bf75b7669a57
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583241"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>エッジの展開を検証Skype for Business Server
 
**概要:** エッジ サーバーまたはエッジ サーバー プールの展開が、エッジ サーバー プールで動作Skype for Business Server。
  
エッジ サーバーまたはエッジ サーバー プールを展開したら、適切に動作しているかどうか知る必要があります。 エッジ環境が内部サーバーに接続されていることを確認し、外部ユーザーがエッジを介して Skype for Business Server 環境に接続できる方法を次に示します。
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>内部サーバーとエッジ サーバー間の接続を確認する

エッジ サーバーがインストールされている場合は、エッジ サーバーまたはエッジ サーバー プールで接続の検証が自動的に行われますが、この確認は引き続きWindows PowerShell。 サーバーの全体Get-CsManagementStoreReplicationStatusストアを持つ内部サーバー、または Skype for Business Server Core Components (OcsCore.msi) がインストールされているドメインに参加しているコンピューターで、OcsCore.msi コマンドレットを実行します。
  
このコマンドを実行した最初の結果は、レプリケーションの場合は True ではなく False 状態になります。 その場合は、このコマンドレットInvoke-CsManagementStoreReplication実行します。 レプリケーションを完了するために少し時間を与え、もう一度Get-CsManagementStoreReplicationStatus実行します。
  
## <a name="verify-connectivity-for-your-external-users"></a>外部ユーザーの接続を確認する

エッジ サーバーの構成を確認するための素晴らしいツールと、エッジ サーバーのシナリオに対して正しいメッセージを接続、送信、受信する機能があります。 これは、リモート [接続 Anaylzer サイトです](https://testconnectivity.microsoft.com/)。 これは、Microsoft サポートによって管理および管理されているサイトです。 このツールを使用するには、Web サイトを参照し、指示に従って適切なシナリオを選択します。
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>外部ユーザー接続をテストする際に考慮すべき点

外部ユーザー アクセスのテストには、組織がサポートする内部ユーザーの種類ごとに含める必要があります。以下の一部またはすべてが含まれる場合があります。
  
- 少なくとも 1 つのフェデレーション ドメインのユーザー (すべてテストすることをお勧めします)。
    
- 匿名ユーザー。
    
- リモートでログインしているが、VPN をSkype for Business組織内のユーザー。
    
これらのテストでは、エッジ サーバーが次のかどうかを判断します。
  
- ネットワーク外から telnet クライアントを使用して必要なポートをリッスンする。
    
  - 例: telnet sip.contoso.com 443
    
  - 展開に応じて、エッジ サーバーまたはエッジ サーバー プールで使用しているポートで、前のテストを実行する必要があります。
    
- 正確な外部 DNS 解決を実行する。
    
  - ネットワークの外部から、エッジ サーバーまたはエッジ サーバー プールの各外部 FQDN に ping を実行します。 ping が失敗した場合でも、IP アドレスが表示され、以前に割り当てた IP アドレスを比較できます。
    

