---
title: ディレクター Web サービスの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がhttps://pool01.contoso.netの場合、ベース url は pool01.contoso.net になります。
ms.openlocfilehash: e62adfb080886397de51ff4c51c5fac19878eeff
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685320"
---
# <a name="add-director-web-service"></a>ディレクター Web サービスの追加
 
ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がhttps://pool01.contoso.netの場合、ベース url は pool01.contoso.net になります。
  
1つのディレクターのみを展開する場合は、内部 Web サービスプールの完全修飾ドメイン名 (FQDN) を上書きすることはできません。 ディレクターのプールのドメインネームシステム (DNS) 負荷分散を構成する場合は、別の内部ベース URL を指定できます (プールの FQDN とは異なる場合があります。これは、プールの\<FQDN とは\>異なる場合があります。これは、内部のベース url などの場合もあります)。
  
ドメイン名を区別するために、内部ベース URL とは異なる外部ベース URL を指定することができます。 たとえば、内部ドメインは contoso.net ですが、外部ドメイン名は contoso.com です。 外部ベース URL を定義するには、contoso.com ドメイン名を使用します。 これは、エッジ展開用のリバースプロキシサーバーにとって重要です。 外部ベース URL ドメイン名は、リバースプロキシの FQDN のドメイン名と同じにする必要があります。 
  

