---
title: 音声ビデオ MCU プールの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: 一元管理されていない A/V 会議サービスがない中央サイトのすべての Enterprise Edition のフロントエンドサーバーは、同じスタンドアロンの A/V 会議プールを使用できます。 各 A/V の会議プールについては、プールに完全修飾ドメイン名 (FQDN) を指定する必要があります。また、1つの A/V 会議サーバーのみを使用するか、または複数の負荷分散された A/V 会議サーバーのみを使用するかを指定する必要があります。
ms.openlocfilehash: 1d78a9d24659ec2ad571c01528323796e7ae5d18
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821319"
---
# <a name="add-av-mcu-pool"></a>音声ビデオ MCU プールの追加
 
一元管理されていない A/V 会議サービスがない中央サイトのすべての Enterprise Edition のフロントエンドサーバーは、同じスタンドアロンの A/V 会議プールを使用できます。 各 A/V の会議プールについては、プールに完全修飾ドメイン名 (FQDN) を指定する必要があります。また、1つの A/V 会議サーバーのみを使用するか、または複数の負荷分散された A/V 会議サーバーのみを使用するかを指定する必要があります。
  
> [!IMPORTANT]
> 単一サーバープールを複数サーバープールに変換することはできません。 組織に複数のサーバープールが必要であると判断された場合は、単一サーバープールを削除してから、複数サーバープールを追加する必要があります。 
  
> [!TIP]
> 今後、A/V 会議プールを実装する予定がある場合は、[**複数のコンピュータープール**] を選びます。 プールが負荷分散された 2 つ以上のコンピューターとして定義されている場合でも、単一コンピューター プールを作成して、単一コンピューターにプールの FQDN を作成することができます。 後でプールにコンピューターを追加する準備ができたら、もう一度トポロジビルダーを使用して、新しいプールメンバーを定義し、新しいトポロジを公開し、Skype for Business Server Deployment ウィザードを使って新しい A/V 会議プールメンバーを設定する必要があります。 A/V 会議サーバープールは、プールを作成するためにロードバランサーが不要であるという点で固有です。 A/V 会議プールでは、内部での負荷分散が行われ、追加のハードウェアは必要ありません。 
  

