---
title: ディレクター プールの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: ディレクタープールの FQDN を定義するには、負荷分散プール内の2つ以上のディレクターで構成される複数のコンピュータープール、または単一のコンピュータープールを選択します。 また、ディレクタープールまたは単一のディレクターの FQDN に接続するために使用される完全修飾ドメイン名 (FQDN) を入力する必要があります。 ディレクターコンピューターのプールの場合、これは、ハードウェアロードバランサーの仮想 IP のドメインネームシステム (DNS) エントリ、DNS ロードバランシング用の共有 DNS エントリのいずれかです。
ms.openlocfilehash: 150975cedf09c19acac1afffab25f5becf053fe3
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698572"
---
# <a name="add-director-pool"></a>ディレクター プールの追加
 
**ディレクタープールの FQDN を定義**するには、負荷分散プール内の2つ以上のディレクターで構成される複数の**コンピュータープール**、または**単一のコンピュータープール**を選択します。 また、ディレクタープールまたは単一のディレクターの FQDN に接続するために使用される完全修飾ドメイン名 (FQDN) を入力する必要があります。 ディレクターコンピューターのプールの場合、これは、ハードウェアロードバランサーの仮想 IP のドメインネームシステム (DNS) エントリ、DNS ロードバランシング用の共有 DNS エントリのいずれかです。
  
> [!TIP]
> 将来ディレクタープールを実装する予定の場合は、[**複数のコンピュータープール**] を選びます。 プールは負荷分散されている2台以上のコンピューターとして定義されていますが、単一のコンピュータープールを作成し、単一のコンピューターのプール FQDN を作成することができます。 後でプールにコンピューターを追加する準備ができたら、トポロジビルダーをもう一度実行して、新しいプールメンバーを定義し、新しいトポロジを公開し、Skype for Business Server Deployment ウィザードを使って新しいディレクタープールメンバーをセットアップする必要があります。 また、プールの適切なロードバランサーに、ドメインネームシステム (DNS) 負荷分散、またはハードウェアロードバランサー用の新しいプールメンバーを追加する必要があります。 多くの場合、両方の負荷分散システムが用意されています。 新しいメンバーサーバーを両方に追加していることを確認してください。 
  

