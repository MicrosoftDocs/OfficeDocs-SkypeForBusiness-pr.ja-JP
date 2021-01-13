---
title: フロントエンドの Web サービスを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL が次の場合、ベース https://pool01.contoso.net URL はpool01.contoso.net。
ms.openlocfilehash: 171cc8c912e1a1204d07be2c52c0e96bc1369991
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823987"
---
# <a name="add-front-end-web-services"></a>フロント エンドの Web サービスの追加
 
ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL が次の場合、ベース https://pool01.contoso.net URL はpool01.contoso.net。
  
Standard Edition サーバーの内部 Web サービス プールの完全修飾ドメイン名 (FQDN) を上書きすることはできません。 Enterprise Edition フロントエンド プールに対してドメイン ネーム システム (DNS) 負荷分散を構成する場合は、プールの FQDN (internal- など) とは異なる内部ベース URL を指定できます。 \<your base URL\>
  
内部ベース URL とは異なる外部ベース URL を指定して、ドメイン名前付けを区別できます。たとえば、内部ドメインが contoso.net でも、外部ドメイン名が contoso.com になっている場合は、contoso.com ドメイン名を使用して外部ベース URL を定義します。これは、エッジ展開でのリバース プロキシ サーバーで重要になります。外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じである必要があります。インスタント メッセージングおよびプレゼンスでは、フロントエンド プールへの HTTP アクセスが必要です。
  

