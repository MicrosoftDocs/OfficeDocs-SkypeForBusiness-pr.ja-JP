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
- CSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: 併置された音声ビデオ会議サービスのないセントラル サイトのすべての Enterprise Edition フロント エンド サーバーは、同じスタンドアロン音声ビデオ会議プールを使用できます。音声ビデオ会議プールごとに、プールの完全修飾ドメイン名 (FQDN) と、音声ビデオ会議サーバーが 1 つだけなのか、または負荷分散された複数の音声ビデオ会議サーバーが存在するのかを指定する必要があります。
ms.openlocfilehash: e38bcf5efa065ef2f9b53a5df47f6a56eafbe29a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217478"
---
# <a name="add-av-mcu-pool"></a>音声ビデオ MCU プールの追加
 
併置された音声ビデオ会議サービスのないセントラル サイトのすべての Enterprise Edition フロント エンド サーバーは、同じスタンドアロン音声ビデオ会議プールを使用できます。音声ビデオ会議プールごとに、プールの完全修飾ドメイン名 (FQDN) と、音声ビデオ会議サーバーが 1 つだけなのか、または負荷分散された複数の音声ビデオ会議サーバーが存在するのかを指定する必要があります。
  
> [!IMPORTANT]
> 単一サーバー プールを複数サーバー プールに変換することはできません。その後、組織で複数サーバー プールが必要となった場合には、単一サーバー プールを削除してから複数サーバー プールを追加する必要があります。 
  
> [!TIP]
> 将来的に音声ビデオ会議プールを実装する予定の場合は、[**複数コンピューターのプール**] を選択してください。 プールを負荷分散された 2 つ以上のコンピューターとして定義する場合でも、単一コンピューターのプールを作成し、その単一コンピューターにプールの FQDN を作成できます。 後でプールにコンピューターを追加する準備ができたら、もう一度トポロジビルダーを使用して、新しいプールメンバーを定義し、新しいトポロジを公開してから、Skype for Business Server 展開ウィザードを使用して新しい音声ビデオ会議プールメンバーをセットアップする必要があります。 音声ビデオ会議サーバー プールは、プールの作成にロード バランサーを必要としない特殊なプールです。 音声ビデオ会議プールでは負荷分散が内部的に行われるので、追加ハードウェアは不要です。 
  

