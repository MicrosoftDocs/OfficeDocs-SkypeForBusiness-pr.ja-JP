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
localization_priority: Normal
description: Skype for Business Server 2019 では、複数サイトと複数プールの展開がサポートされています。 複数のプールを Skype for Business Server 2019 に移行するプロセスには、以下の点を考慮する必要があります。
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752659"
---
# <a name="migrating-multiple-sites-and-pools"></a>複数のサイトとプールの移行

Skype for Business Server 2019 では、複数サイトと複数プールの展開がサポートされています。 複数のプールを Skype for Business Server 2019 に移行するプロセスには、以下の点を考慮する必要があります。 
  
1. Skype for business Server 2019 パイロットプールを展開した後、Skype for Business Server 2019 プールに移動するパイロットユーザーのサブセットと、ユーザーの機能を検証するための方法を定義する必要があります。 たとえば、ユーザーをパイロットプールに移動した後、ユーザーの会議ポリシーが Skype for Business Server 2019 に移動されたことを確認します。 
    
2. パイロットプールにエッジサーバーを展開した後、外部ユーザーが Skype for Business Server 2019 プールと通信できることを検証する必要があります。

3. 常設チャット、SQL ミラーリング、および XMPP の機能は、Skype for business Server 2019 では廃止され、Skype for Business Server 2019 の機能として使用できなくなりましたが、従来の環境で展開されていた場合は、共存環境で続行できます。 これらの機能を引き続き使用する場合は、特定のユーザーが従来のプールにとどまることがある共存環境で続行することを計画する必要があります。
    
4. フェデレーションルートのエッジサーバーを、パイロットの Skype for Business Server 2019 エッジサーバーに移行した後、フェデレーションユーザーが Skype for Business Server 2019 プールと通信できることを検証する必要があります。
    
5. すべてのユーザーおよびユーザー以外の連絡先オブジェクトを移動した後、従来のプールが空であることを確認する必要があります。
    
6. 従来のプールが空であることを確認した後、プールを非アクティブ化することができます。 
    
    従来のプールおよびサーバーを非アクティブ化する方法の詳細については、「[フェーズ 8: 従来のプール](phase-8-decommission-legacy-pools.md)を使用停止にする」を参照してください。
    

