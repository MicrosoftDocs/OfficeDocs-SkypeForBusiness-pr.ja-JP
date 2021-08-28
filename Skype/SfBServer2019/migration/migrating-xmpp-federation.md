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
ms.localizationpriority: medium
description: 以前のバージョンでは、XMPP 展開とのフェデレーションを可能にする別のサーバー役割として展開できる拡張可能なメッセージングおよびプレゼンス プロトコル (XMPP) ゲートウェイが提供されました。 XMPP 機能は、2019 年&で使用Skype for Business Serverなくなりました。 XMPP 機能を続行する場合は、従来のバージョン (Skype for Business Server 2015/ Lync Server 2013) と共に使用できます。 XMPP 機能は、従来のエッジ サーバー上で実行される XMPP プロキシと、従来のフロント エンド サーバーで実行される XMPP ゲートウェイの 2 つの部分にインストールされます。
ms.openlocfilehash: a0c3eeaa6218c6e3b3726f755adcca6083a9ac3f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580131"
---
# <a name="migrating-xmpp-federation"></a>XMPP フェデレーションの移行

以前のバージョンでは、XMPP 展開とのフェデレーションを可能にする別のサーバー役割として展開できる拡張可能なメッセージングおよびプレゼンス プロトコル (XMPP) ゲートウェイが提供されました。 XMPP 機能は使用できなくなったので、2019 年Skype for Business Serverされています。 XMPP 機能を続行する場合は、従来のバージョン (Skype for Business Server 2015 または Lync Server 2013) との共存環境で実行できます。 XMPP 機能は、従来のエッジ サーバー上で実行される XMPP プロキシと、従来のフロント エンド サーバーで実行される XMPP ゲートウェイの 2 つの部分にインストールされます。 
  
移行の観点から、XMPP 機能を利用するユーザーは従来のサーバーに残り、Skype for Business Server 2019 プールに移動する必要がありますが、従来の XMPP ゲートウェイを引き続き使用する必要があります。 これは、XMPP フェデレーション パートナーが 2015 年または Lync Server 2013 で構成Skype for Business Server場合にのみ可能です。 XMPP 機能を続行する場合は、従来のエッジ サーバーを 2019 Skype for Business Server 2019 に移行する必要があります。 ただし、従来のエッジ サーバー (XMPP プロキシを使用) と 2019 エッジ Skype for Business共存させることができます。
  

    

