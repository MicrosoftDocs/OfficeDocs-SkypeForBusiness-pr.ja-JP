---
title: A/V MCU プールの追加
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
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: 併置された音声ビデオ会議サービスのないセントラル サイトのすべての Enterprise Edition フロント エンド サーバーは、同じスタンドアロン音声ビデオ会議プールを使用できます。音声ビデオ会議プールごとに、プールの完全修飾ドメイン名 (FQDN) と、音声ビデオ会議サーバーが 1 つだけなのか、または負荷分散された複数の音声ビデオ会議サーバーが存在するのかを指定する必要があります。
ms.openlocfilehash: 212b9294a1e1d3578652e595cccb72088d859685
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628109"
---
# <a name="add-av-mcu-pool"></a>A/V MCU プールの追加
 
併置された音声ビデオ会議サービスのないセントラル サイトのすべての Enterprise Edition フロント エンド サーバーは、同じスタンドアロン音声ビデオ会議プールを使用できます。音声ビデオ会議プールごとに、プールの完全修飾ドメイン名 (FQDN) と、音声ビデオ会議サーバーが 1 つだけなのか、または負荷分散された複数の音声ビデオ会議サーバーが存在するのかを指定する必要があります。
  
> [!IMPORTANT]
> 単一サーバー プールを複数サーバー プールに変換することはできません。その後、組織で複数サーバー プールが必要となった場合には、単一サーバー プールを削除してから複数サーバー プールを追加する必要があります。 
  
> [!TIP]
> 将来的に音声ビデオ会議プールを実装する予定の場合は、[**複数コンピューターのプール**] を選択してください。 プールを負荷分散された 2 つ以上のコンピューターとして定義する場合でも、単一コンピューターのプールを作成し、その単一コンピューターにプールの FQDN を作成できます。 後でプールにコンピューターを追加する準備ができたら、トポロジ ビルダーで新しいプール メンバーを定義し、新しいトポロジを発行し、Skype for Business Server 展開ウィザードを使用して新しい音声ビデオ会議プール メンバーをセットアップする必要があります。 音声ビデオ会議サーバー プールは、プールの作成にロード バランサーを必要としない特殊なプールです。 音声ビデオ会議プールでは負荷分散が内部的に行われるので、追加ハードウェアは不要です。 
  

