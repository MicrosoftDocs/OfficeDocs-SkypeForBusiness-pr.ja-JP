---
title: Skype for Business Server 2015 でのエッジ展開の検証
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: '概要: は、Skype のビジネス サーバー 2015 のエッジ サーバーまたはエッジ サーバー プールの展開が機能していることを確認する方法を説明します。'
ms.openlocfilehash: b8adc5e8d652607156d0136671b1f149fbfe27b4
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 でのエッジ展開の検証
 
**の概要:** ビジネス サーバー 2015 の Skype でエッジ サーバーまたはエッジ サーバー プールの展開が機能していることを確認する方法について説明します。
  
エッジ サーバーまたはエッジ サーバー プールを展開して、正しく動作しているかを把握する必要があります。 エッジ環境に接続されていることを確認するのに役立ついくつかをここでは、内部のサーバーに、外部ユーザー経由で接続できるサーバー 2015 のビジネス環境について、Skype、エッジです。
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>内部サーバーとエッジ サーバーの間の接続を検証する

接続の検証は、エッジ トランスポート サーバーがインストールされている場合も、エッジ サーバーまたはエッジ サーバー プールに自動的に行われます、中にも確認できます自分用の Windows PowerShell にします。 保存、一元管理があるか、ビジネス サーバー 2015 のコア ・ コンポーネント (OcsCore.msi) は、Skype 上の任意のドメイン結合されたコンピューターがインストールされている内部サーバー上には、Get CsManagementStoreReplicationStatus コマンドレットを実行します。
  
このコマンドを実行した最初の結果では、レプリケーションに対して、状態が True ではなく False と示される場合があります。その場合は Invoke-CsManagementStoreReplication コマンドレットを実行し、レプリケーションが完了するまでしばらく待ってから、再び Get-CsManagementStoreReplicationStatus コマンドレットを実行します。
  
## <a name="verify-connectivity-for-your-external-users"></a>外部ユーザーの接続を検証する

エッジ サーバーの構成と接続、送信、およびエッジ サーバーのシナリオで適切なメッセージを受信することを確認するための優れたツールあります。 これは、[リモート接続 Anaylzer サイト](https://testconnectivity.microsoft.com/)です。 このサイトは Microsoft サポートにより管理および維持されています。 このツールを使用するには、上記の Web サイトにアクセスし、適切なシナリオを選択するための指示に従います。
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>外部ユーザーの接続をテストする際の考慮事項

外部ユーザー アクセスのテストには、次のいずれかまたはすべてなど、組織がサポートしている各内部ユーザー タイプを含める必要があります。
  
- 少なくとも 1 つのフェデレーション ドメインのユーザー (ただしすべてのユーザーのテストは推奨しません)。
    
- 匿名ユーザー。
    
- ユーザー、組織内にビジネス用の Skype、リモートでログに記録されますが、VPN を使用していません。
    
これらのテストには、エッジ サーバーがあるかどうかが決まります。
  
- ネットワーク外から telnet クライアントを使用して必要なポートをリッスンする。
    
  - 例: telnet sip.contoso.com 443
    
  - 配置に基づいて、エッジ サーバーまたはエッジ サーバーのプールで使用するポートで上記のテストを行う必要があります。
    
- 正確な外部 DNS 解決を実行する。
    
  - ネットワーク外の外部エッジ サーバーまたはエッジ サーバー プールの Fqdn を ping します。 Ping が失敗した場合でも、以前に割り当てた IP アドレスを比較することができる IP アドレスが表示されます。
    

