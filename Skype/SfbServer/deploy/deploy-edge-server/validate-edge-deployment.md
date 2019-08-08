---
title: Skype for Business Server での Edge の展開を検証する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: '概要: エッジサーバーまたはエッジサーバープールの展開が Skype for Business Server で動作していることを確認する方法について説明します。'
ms.openlocfilehash: 57994e4583a3424fc680c8dfb220aeb11668c6fc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233875"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Skype for Business Server での Edge の展開を検証する
 
**概要:** エッジサーバーまたはエッジサーバープールの展開が Skype for Business Server で動作していることを確認する方法について説明します。
  
エッジサーバーまたはエッジサーバープールを展開したら、正常に動作しているかどうかを確認する必要があります。 ここでは、Edge 環境が内部サーバーに接続されていることを確認するために役立ついくつかの方法について説明します。また、外部ユーザーは、Edge 経由で Skype for Business Server 環境に接続することもできます。
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>内部サーバーとエッジ サーバーの間の接続を検証する

エッジサーバーがインストールされているときに接続の検証がエッジサーバーまたはエッジサーバープールで自動的に行われる場合は、Windows PowerShell を使用してこれを確認することができます。 中央管理ストア、または Skype for Business Server Core Components (OcsCore) がインストールされている任意のドメインに参加しているコンピューターで、CsManagementStoreReplicationStatus コマンドレットを実行します。
  
このコマンドを実行した最初の結果では、レプリケーションに対して、状態が True ではなく False と示される場合があります。その場合は Invoke-CsManagementStoreReplication コマンドレットを実行し、レプリケーションが完了するまでしばらく待ってから、再び Get-CsManagementStoreReplicationStatus コマンドレットを実行します。
  
## <a name="verify-connectivity-for-your-external-users"></a>外部ユーザーの接続を検証する

エッジサーバーの構成を確認するための優れたツールが用意されています。また、エッジサーバーのシナリオについて、適切なメッセージの接続、送受信、受信を行うことができます。 これは、[リモート接続 Anaylzer サイト](https://testconnectivity.microsoft.com/)です。 このサイトは Microsoft サポートにより管理および維持されています。 このツールを使用するには、上記の Web サイトにアクセスし、適切なシナリオを選択するための指示に従います。
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>外部ユーザーの接続をテストする際の考慮事項

外部ユーザー アクセスのテストには、次のいずれかまたはすべてなど、組織がサポートしている各内部ユーザー タイプを含める必要があります。
  
- 少なくとも 1 つのフェデレーション ドメインのユーザー (ただしすべてのユーザーのテストは推奨しません)。
    
- 匿名ユーザー。
    
- リモートで Skype for Business にログインしているが、VPN を使用していない組織内のユーザー。
    
これらのテストによって、エッジサーバーが次のどちらであるかが判別されます。
  
- ネットワーク外から telnet クライアントを使用して必要なポートをリッスンする。
    
  - 例: telnet sip.contoso.com 443
    
  - 展開に応じて、エッジサーバーまたはエッジサーバープールで使用しているポートに対して、前のテストを実行する必要があります。
    
- 正確な外部 DNS 解決を実行する。
    
  - ネットワークの外部から、エッジサーバーまたはエッジサーバープールの外部 Fqdn をそれぞれ ping します。 Ping に失敗した場合でも、IP アドレスが表示されます。これにより、以前に割り当てた IP アドレスを比較できます。
    

