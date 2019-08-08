---
title: XMPP フェデレーションの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 以前のバージョンでは、拡張メッセージングとプレゼンスプロトコル (XMPP) ゲートウェイが提供されていました。このゲートウェイは、別のサーバーロールとして展開して、XMPP の展開とのフェデレーションを可能にします。 XMPP 機能は、Skype for Business Server 2019 で廃止された & 利用できなくなりました。 引き続き XMPP 機能を使用できるようにする場合は、旧バージョン (Skype for Business Server 2015/Lync Server 2013) を使って coexitence 使用環境で利用できます。 XMPP 機能は、従来のエッジサーバー上で実行される XMPP プロキシとして、従来のフロントエンドサーバー上で実行される XMPP ゲートウェイとして、2つの部分にインストールされます。
ms.openlocfilehash: 0c7c3dbb9c7cda4f6825f66326422dced85a9c3c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237794"
---
# <a name="migrating-xmpp-federation"></a>XMPP フェデレーションの移行

以前のバージョンでは、拡張メッセージングとプレゼンスプロトコル (XMPP) ゲートウェイが提供されていました。このゲートウェイは、別のサーバーロールとして展開して、XMPP の展開とのフェデレーションを可能にします。 XMPP 機能は使用できなくなり、Skype for Business Server 2019 では廃止されました。 引き続き XMPP 機能を使用する場合は、以前のバージョン (Skype for Business Server 2015 または Lync Server 2013) を使用した共存環境で行うことができます。 XMPP 機能は、従来のエッジサーバー上で実行される XMPP プロキシとして、従来のフロントエンドサーバー上で実行される XMPP ゲートウェイとして、2つの部分にインストールされます。 
  
移行の観点から、XMPP 機能を利用したいユーザーは従来のサーバーに残しておく必要があります。 Skype for Business Server 2019 プールには移動せず、従来の XMPP ゲートウェイの使用を続行してください。 これは、Skype for Business Server 2015 または Lync Server 2013 で XMPP フェデレーションパートナーが構成されている場合にのみ可能です。 引き続き XMPP 機能を使用する場合は、従来のエッジサーバーを Skype for Business Server 2019 に移行しないでください。 ただし、従来のエッジサーバー (XMPP プロキシ付き) と Skype for Business 2019 Edge サーバーの共存は可能です。
  

    

