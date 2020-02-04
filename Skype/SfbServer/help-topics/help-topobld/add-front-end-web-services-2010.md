---
title: フロントエンドの Web サービスの追加 (2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がhttps://pool01.contoso.netの場合、ベース url は pool01.contoso.net になります。
ms.openlocfilehash: 48d2cc4c8ce9bc1074ae42e385265b34f24c662e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685130"
---
# <a name="add-front-end-web-services-2010"></a>フロントエンドの Web サービスの追加 (2010)
 
ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がhttps://pool01.contoso.netの場合、ベース url は pool01.contoso.net になります。
  
Standard Edition サーバーの内部 Web サービスプールの完全修飾ドメイン名 (FQDN) を上書きすることはできません。 Enterprise Edition のフロントエンドプールでドメインネームシステム (DNS) 負荷分散を構成している場合は、別の内部ベース URL (プールの FQDN と異なる場合があります。これはプールの FQDN と異なる\<ことがあり\>ます。これは、ベース url などの場合もあります)。
  
ドメイン名を区別するために、内部ベース URL とは異なる外部ベース URL を指定することができます。 たとえば、内部ドメインは contoso.net ですが、外部ドメイン名は contoso.com です。 外部ベース URL を定義するには、contoso.com ドメイン名を使用します。 これは、エッジ展開用のリバースプロキシサーバーにとって重要です。 外部ベース URL ドメイン名は、リバースプロキシの FQDN のドメイン名と同じにする必要があります。 インスタントメッセージングとプレゼンスを使用するには、フロントエンドプールへの HTTP アクセスが必要です。
  

