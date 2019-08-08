---
title: 複数のサイトとプールの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 2019 は、複数サイトと複数プールの展開をサポートしています。 複数のプールを Skype for Business Server 2019 に移行するプロセスには、次の考慮事項があります。
ms.openlocfilehash: e2577b6af1430be90e30fff3236d7ea3cf473cd5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237875"
---
# <a name="migrating-multiple-sites-and-pools"></a>複数のサイトとプールの移行

Skype for Business Server 2019 は、複数サイトと複数プールの展開をサポートしています。 複数のプールを Skype for Business Server 2019 に移行するプロセスには、次の考慮事項があります。 
  
1. Skype for Business Server 2019 パイロットプールを展開した後、Skype for Business Server 2019 プールに移動されるパイロットユーザーのサブセットと、ユーザーの機能を検証するための方法を定義する必要があります。 たとえば、パイロットプールにユーザーを移動した後、ユーザーの会議ポリシーが Skype for Business Server 2019 に移行されたことを確認します。 
    
2. パイロットプールにエッジサーバーを展開した後、外部ユーザーが Skype for Business Server 2019 プールと通信できることを検証する必要があります。

3. 永続的なチャット、SQL ミラーリング、および XMPP 機能は、Skype for Business Server 2019 では廃止され、Skype for Business Server 2019 機能としては利用できなくなりましたが、以前に展開したことがある場合は、共存環境で続行できます。従来の環境。 これらの機能を引き続き使用する場合は、特定のユーザーが従来のプールにとどまることができる共存環境を継続することを計画する必要があります。
    
4. フェデレーションルートのエッジサーバーをパイロット版の Skype for Business Server 2019 Edge サーバーに移行した後、フェデレーションされたユーザーが Skype for Business Server 2019 プールと通信できることを検証する必要があります。
    
5. すべてのユーザーと非ユーザーの連絡先オブジェクトを移動した後、従来のプールが空であることを確認する必要があります。
    
6. 従来のプールが空であることを確認した後、プールを非アクティブ化することができます。 
    
    従来のプールとサーバーを非アクティブ化する方法について詳しくは、「[フェーズ 8: レガシプールの廃止](phase-8-decommission-legacy-pools.md)」をご覧ください。
    

