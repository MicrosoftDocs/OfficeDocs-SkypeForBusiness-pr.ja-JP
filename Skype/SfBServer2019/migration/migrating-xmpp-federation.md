---
title: XMPP フェデレーションの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '以前のバージョンでは、拡張可能なメッセージングおよびプレゼンス プロトコル (XMPP) ゲートウェイ XMPP 環境とのフェデレーションを許可する個別のサーバーの役割として展開されているが用意されています。 XMPP 機能が利用可能な & のビジネス サーバー 2019 の Skype では非推奨ではありません。 従来のバージョンと coexitence の環境で有効 XMPP の機能を続行する場合を (ビジネス サーバー 2015 の Skype と Lync Server 2013) です。 XMPP の機能は 2 つの部分のインストール: として、XMPP プロキシ上で動作する従来のエッジ サーバー、および XMPP ゲートウェイが従来のフロント エンド サーバー上で実行します。'
ms.openlocfilehash: fa91741c1be8d80443363caba7c840b1d985d8f4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231631"
---
# <a name="migrating-xmpp-federation"></a>XMPP フェデレーションの移行

以前のバージョンでは、拡張可能なメッセージングおよびプレゼンス プロトコル (XMPP) ゲートウェイ XMPP 環境とのフェデレーションを許可する個別のサーバーの役割として展開されているが用意されています。 XMPP 機能は使用できなくし、ビジネス サーバー 2019 の Skype では非推奨です。 XMPP の機能を続行する場合は、これを行う従来のバージョン (Skype ビジネス サーバー 2015 または Lync Server 2013) との共存環境にします。 XMPP の機能は 2 つの部分のインストール: として、XMPP プロキシ上で動作する従来のエッジ サーバー、および XMPP ゲートウェイが従来のフロント エンド サーバー上で実行します。 
  
移行の観点から、XMPP の機能を利用するユーザー レガシー サーバーで維持する必要があります、ビジネス サーバー 2019 プール、Skype に移動する必要がありますですが、従来の XMPP ゲートウェイを使用し続けます。 XMPP フェデレーション パートナーがビジネス サーバー 2015 または Lync Server 2013 の Skype で構成されている場合にのみ可能です。 ビジネス サーバー 2019 の Skype には、XMPP の機能を続行する場合は、レガシー エッジ サーバーを移行する必要がありますされません。 ただし、レガシ (使用してエッジ サーバー XMPP プロキシ) とビジネス 2019年エッジ サーバーの Skype の共存することができます。
  

    

