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
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がの場合、 https://pool01.contoso.net ベース url は pool01.contoso.net になります。
ms.openlocfilehash: d87bb3716a19f59f2614194d79dfedaf544964e1
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217958"
---
# <a name="add-front-end-web-services-2010"></a>フロントエンドの Web サービスの追加 (2010)
 
ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がの場合、 https://pool01.contoso.net ベース url は pool01.contoso.net になります。
  
Standard Edition サーバーの内部 Web サービスプールの完全修飾ドメイン名 (FQDN) を上書きすることはできません。 Enterprise Edition フロントエンドプールに対してドメインネームシステム (DNS) 負荷分散を構成している場合は、異なる内部ベース URL を指定できます (プールの FQDN とは異なる必要があり、たとえば、内部 \<your base URL\> )。
  
内部ベース URL とは異なる外部ベース URL を指定して、ドメイン名前付けを区別できます。 たとえば、内部ドメインは contoso.net ですが、外部ドメイン名は contoso.com という場合があります。 ドメイン名 contoso.com を使用して、外部ベース URL を定義しています。 これは、エッジ展開でのリバース プロキシ サーバーで重要になります。 外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じである必要があります。 インスタントメッセージングとプレゼンスは、フロントエンドプールへの HTTP アクセスを必要とします。
  

