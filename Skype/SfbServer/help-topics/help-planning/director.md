---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: ディレクターは、Skype for Business Server 2015 通信ソフトウェアを実行していて、ユーザー要求を認証することはできますが、ユーザーアカウントのホームにはなりません。
ms.openlocfilehash: 2abb3cac867771ecd46c233be5864779512d39da
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821519"
---
# <a name="director-planning-tool"></a>Director (Planning Tool)
 
ディレクターは、Skype for Business Server 2015 通信ソフトウェアを実行していて、ユーザー要求を認証することはできますが、ユーザーアカウントのホームにはなりません。 
  
この役割はオプションであり、次の2つのシナリオでディレクターを展開することを選択します。
  
- エッジサーバーを展開して外部ユーザーからのアクセスを有効にする場合は、ディレクターも展開する必要があります。 このシナリオでは、ディレクターが外部ユーザーを認証し、そのトラフィックを内部サーバーに渡します。 ディレクターを使用して外部ユーザーを認証すると、フロントエンドプールサーバーは、これらのユーザーの認証を実行するオーバーヘッドから解放されます。 また、サービス拒否攻撃などの悪意のあるトラフィックから、内部のフロントエンドプールを分離することもできます。 このような攻撃で無効な外部トラフィックがネットワークにあふれている場合、このトラフィックはディレクターで終了します。
    
- セントラルサイトに複数のフロントエンドプールを展開している場合、そのサイトにディレクターを追加すると、認証要求が簡素化され、パフォーマンスが向上します。 このシナリオでは、すべての要求が最初にディレクターに送られ、適切なフロントエンドプールに転送されます。
    

