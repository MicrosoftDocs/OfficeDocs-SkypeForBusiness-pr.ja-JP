---
title: フロントエンド コンピューターの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: このプールでフロントエンドサーバーとして追加する各コンピューターの完全修飾ドメイン名 (FQDN) を指定します。 一覧にコンピューターを追加した後でも、トポロジを公開するまでの間は、いつでもコンピューターの FQDN を更新したり、プールからコンピューターを削除したりできます。 トポロジを公開した後、FQDN を変更するには、トポロジビルダーでサーバーを削除してから新しい FQDN のプールに新しいサーバーを追加する必要があります。 トポロジへのフロントエンドプールの追加について詳しくは、「展開ドキュメントでフロントエンドプールを定義して構成する」をご覧ください。
ms.openlocfilehash: a4ff4ce7a7fc775e33657dc2f8602d62163ed1d4
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798544"
---
# <a name="add-front-end-machine"></a>フロントエンド コンピューターの追加

このプールでフロントエンドサーバーとして追加する各コンピューターの完全修飾ドメイン名 (FQDN) を指定します。 一覧にコンピューターを追加した後でも、トポロジを公開するまでの間は、いつでもコンピューターの FQDN を更新したり、プールからコンピューターを削除したりできます。 トポロジを公開した後、FQDN を変更するには、トポロジビルダーでサーバーを削除してから新しい FQDN のプールに新しいサーバーを追加する必要があります。 トポロジへのフロントエンドプールの追加について詳しくは、「展開ドキュメントで[フロントエンドプールを定義して構成](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)する」をご覧ください。

> [!IMPORTANT]
> トポロジビルダーでは、1つのプールに最大20台のフロントエンドサーバーを含めることができることを確認します。 サポートされているサーバーの最大数は12です。 ファブリックには最大20の statefull サーバーを定義できます。これは、どの時点でもアクティブとオンラインにすることができます。


