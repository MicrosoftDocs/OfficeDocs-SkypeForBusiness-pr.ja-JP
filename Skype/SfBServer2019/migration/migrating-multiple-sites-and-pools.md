---
title: 複数のサイトとプールの移行
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
description: Skype for Business Server 2019 では、マルチサイト展開とマルチプール展開がサポートされています。 2019 年に複数のプールを 2019 Skype for Business Serverするには、次の考慮事項が必要です。
ms.openlocfilehash: 514c606b580f0602ebf8ce6b1a41e553445aa4f2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613384"
---
# <a name="migrating-multiple-sites-and-pools"></a>複数のサイトとプールの移行

Skype for Business Server 2019 では、マルチサイト展開とマルチプール展開がサポートされています。 2019 年に複数のプールを 2019 Skype for Business Serverするには、次の考慮事項が必要です。 
  
1. Skype for Business Server 2019 パイロット プールを展開した後、Skype for Business Server 2019 プールに移動するパイロット ユーザーのサブセットと、ユーザーの機能を検証するための方法を定義する必要があります。 たとえば、ユーザーをパイロット プールに移動した後、ユーザーの会議ポリシーが 2019 年に移行Skype for Business Serverします。 
    
2. パイロット プールにエッジ サーバーを展開した後、外部ユーザーが 2019 プールと通信Skype for Business Server必要があります。

3. 常設チャット、SQL ミラーリング、および XMPP 機能は、Skype for Business Server 2019 では廃止され、Skype for Business Server 2019 の機能として使用できなくなりましたが、従来の環境で以前に展開されている場合は共存環境で継続できます。 これらの機能を引き続き使用する場合は、特定のユーザーが従来のプールに残る共存環境を継続する予定です。
    
4. フェデレーション ルートのエッジ サーバーをパイロット Skype for Business Server 2019 エッジ サーバーに移行した後、フェデレーション ユーザーが Skype for Business Server 2019 プールと通信できる状態を検証する必要があります。
    
5. すべてのユーザーとユーザー以外の連絡先オブジェクトを移動した後、レガシ プールが空であるのを検証する必要があります。
    
6. レガシ プールが空の場合は、プールを非アクティブ化できます。 
    
    従来のプールとサーバーを非アクティブ化する方法の詳細については、「フェーズ 8: 従来のプールを使用停止 [する」を参照してください](phase-8-decommission-legacy-pools.md)。
    

