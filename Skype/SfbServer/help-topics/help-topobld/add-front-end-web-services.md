---
title: フロントエンドの Web サービスの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がhttps://pool01.contoso.netの場合、ベース url は pool01.contoso.net になります。
ms.openlocfilehash: 10749cc746cf1f3d039a89fd351be6de77eafaee
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698202"
---
# <a name="add-front-end-web-services"></a>フロントエンドの Web サービスの追加
 
ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がhttps://pool01.contoso.netの場合、ベース url は pool01.contoso.net になります。
  
Standard Edition サーバーの内部 Web サービスプールの完全修飾ドメイン名 (FQDN) を上書きすることはできません。 Enterprise Edition のフロントエンドプールでドメインネームシステム (DNS) 負荷分散を構成する場合、別の内部ベース URL を指定することができます。この URL はプールの FQDN (内部\<のベース url\>など) とは異なることがあります。
  
ドメイン名を区別するために、内部ベース URL とは異なる外部ベース URL を指定することができます。 たとえば、内部ドメインは contoso.net ですが、外部ドメイン名は contoso.com です。 Contoso.com ドメイン名を使用して、外部ベース URL を定義することができます。 これは、エッジ展開用のリバースプロキシサーバーにとって重要です。 外部ベース URL ドメイン名は、リバースプロキシの FQDN のドメイン名と同じにする必要があります。 インスタントメッセージングとプレゼンスを使用するには、フロントエンドプールへの HTTP アクセスが必要です。
  

