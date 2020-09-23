---
title: フロントエンドの Web サービスを追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がの場合、 https://pool01.contoso.net ベース url は pool01.contoso.net になります。
ms.openlocfilehash: 45705ea940fa0f43f600546a680d76b41b645e59
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217938"
---
# <a name="add-front-end-web-services"></a>フロントエンドの Web サービスを追加する
 
ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がの場合、 https://pool01.contoso.net ベース url は pool01.contoso.net になります。
  
Standard Edition サーバーの内部 Web サービスプールの完全修飾ドメイン名 (FQDN) を上書きすることはできません。 Enterprise Edition フロントエンドプールに対してドメインネームシステム (DNS) 負荷分散を構成している場合は、プールの FQDN (たとえば、内部) とは異なる内部ベースの URL を指定することができ \<your base URL\> ます。
  
内部ベース URL とは異なる外部ベース URL を指定して、ドメイン名前付けを区別できます。たとえば、内部ドメインが contoso.net でも、外部ドメイン名が contoso.com になっている場合は、contoso.com ドメイン名を使用して外部ベース URL を定義します。これは、エッジ展開でのリバース プロキシ サーバーで重要になります。外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じである必要があります。インスタント メッセージングおよびプレゼンスでは、フロントエンド プールへの HTTP アクセスが必要です。
  

