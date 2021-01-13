---
title: フロント エンドの Web サービスの追加 (2010)
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
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL が次の場合、ベース https://pool01.contoso.net URL はpool01.contoso.net。
ms.openlocfilehash: 96a258cd2d3c46d700dff32ea4adb6213b4de9b1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824027"
---
# <a name="add-front-end-web-services-2010"></a>フロント エンドの Web サービスの追加 (2010)
 
ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL が次の場合、ベース https://pool01.contoso.net URL はpool01.contoso.net。
  
Standard Edition サーバーの内部 Web サービス プールの完全修飾ドメイン名 (FQDN) を上書きすることはできません。 Enterprise Edition フロントエンド プールに対してドメイン ネーム システム (DNS) 負荷分散を構成する場合は、別の内部ベース URL (プールの FQDN とは異なる必要があります。内部 URL など) を指定できます。 \<your base URL\>
  
内部ベース URL とは異なる外部ベース URL を指定して、ドメイン名前付けを区別できます。 たとえば、内部ドメインは contoso.net ですが、外部ドメイン名は contoso.com という場合があります。 ドメイン名 contoso.com を使用して、外部ベース URL を定義しています。 これは、エッジ展開でのリバース プロキシ サーバーで重要になります。 外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じである必要があります。 インスタント メッセージングとプレゼンスでは、フロント エンド プールへの HTTP アクセスが必要です。
  

