---
title: XMPP フェデレーションの移行
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
description: 以前のバージョンでは、XMPP の展開とのフェデレーションを可能にするために、独立したサーバーの役割として展開できる拡張メッセージングおよびプレゼンスプロトコル (XMPP) ゲートウェイが提供されていました。 XMPP 機能は、Skype for Business Server 2019 で廃止された & 使用できなくなりました。 XMPP 機能を引き続き使用する場合は、以前のバージョンの coexitence 環境で利用できます (Skype for Business Server 2015/Lync Server 2013)。 XMPP 機能は、従来のエッジサーバーで実行される XMPP プロキシ、従来のフロントエンドサーバー上で実行される XMPP ゲートウェイとして、2つの部分に分けてインストールされます。
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752649"
---
# <a name="migrating-xmpp-federation"></a>XMPP フェデレーションの移行

以前のバージョンでは、XMPP の展開とのフェデレーションを可能にするために、独立したサーバーの役割として展開できる拡張メッセージングおよびプレゼンスプロトコル (XMPP) ゲートウェイが提供されていました。 XMPP 機能は使用できなくなり、Skype for Business Server 2019 では廃止されました。 XMPP の機能を引き続き使用する場合は、従来のバージョン (Skype for Business Server 2015 または Lync Server 2013) を使用した共存環境でこれを行うことができます。 XMPP 機能は、従来のエッジサーバーで実行される XMPP プロキシ、従来のフロントエンドサーバー上で実行される XMPP ゲートウェイとして、2つの部分に分けてインストールされます。 
  
移行の観点から、XMPP 機能の利用を希望するユーザーは従来のサーバーに残しておく必要があります。ただし、Skype for Business Server 2019 プールに移動する必要はありませんが、従来の XMPP ゲートウェイを引き続き使用する必要があります。 これは、XMPP フェデレーションパートナーが Skype for Business Server 2015 または Lync Server 2013 で構成されている場合にのみ可能です。 XMPP 機能を引き続き使用する場合は、従来のエッジサーバーを Skype for Business Server 2019 に移行しないでください。 ただし、従来のエッジサーバー (XMPP プロキシを使用) と Skype for Business 2019 エッジサーバーを共存させることができます。
  

    

