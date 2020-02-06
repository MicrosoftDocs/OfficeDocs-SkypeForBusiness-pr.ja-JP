---
title: 複数のサイトとプールの移行
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
description: Skype for Business Server 2019 は、複数サイトと複数プールの展開をサポートしています。 複数のプールを Skype for Business Server 2019 に移行するプロセスには、次の考慮事項があります。
ms.openlocfilehash: d1257590c431bc15aad4db03908aa6d95fd5fce3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813445"
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
    

