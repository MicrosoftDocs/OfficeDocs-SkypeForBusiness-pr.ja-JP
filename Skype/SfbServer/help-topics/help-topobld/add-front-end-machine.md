---
title: フロントエンド コンピューターの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: このプールでフロントエンドサーバーとして追加する各コンピューターの完全修飾ドメイン名 (FQDN) を指定します。 一覧にコンピューターを追加した後でも、トポロジを公開するまでの間は、いつでもコンピューターの FQDN を更新したり、プールからコンピューターを削除したりできます。 トポロジを公開した後、FQDN を変更するには、トポロジビルダーでサーバーを削除してから新しい FQDN のプールに新しいサーバーを追加する必要があります。 トポロジへのフロントエンドプールの追加について詳しくは、「展開ドキュメントでフロントエンドプールを定義して構成する」をご覧ください。
ms.openlocfilehash: dd7fdb3e561972071a6af9fee084af1c3cf679f1
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698252"
---
# <a name="add-front-end-machine"></a>フロントエンド コンピューターの追加

このプールでフロントエンドサーバーとして追加する各コンピューターの完全修飾ドメイン名 (FQDN) を指定します。 一覧にコンピューターを追加した後でも、トポロジを公開するまでの間は、いつでもコンピューターの FQDN を更新したり、プールからコンピューターを削除したりできます。 トポロジを公開した後、FQDN を変更するには、トポロジビルダーでサーバーを削除してから新しい FQDN のプールに新しいサーバーを追加する必要があります。 トポロジへのフロントエンドプールの追加について詳しくは、「展開ドキュメントで[フロントエンドプールを定義して構成](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)する」をご覧ください。

> [!IMPORTANT]
> トポロジビルダーでは、1つのプールに最大20台のフロントエンドサーバーを含めることができることを確認します。 サポートされているサーバーの最大数は12です。 ファブリックには最大20の statefull サーバーを定義できます。これは、どの時点でもアクティブとオンラインにすることができます。


