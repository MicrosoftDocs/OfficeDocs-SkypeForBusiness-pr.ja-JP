---
title: フロントエンド コンピューターを追加する
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: このプールにフロント エンド サーバーとして追加する各コンピューターの完全修飾ドメイン名 (FQDN) を指定します。一覧にコンピューターを追加した後、トポロジを公開するまでの間はいつでも、コンピューターの FQDN を更新したり、プールからコンピューターを削除したりできます。トポロジの公開後に FQDN を変更するには、トポロジ ビルダーでサーバーを削除し、新しいサーバーを新しい FQDN でプールに追加する必要があります。トポロジへのフロント エンド プールの追加の詳細については、「展開」のドキュメントの「Define and Configure a Front End Pool (フロント エンド プールの定義および構成)」を参照してください。
ms.openlocfilehash: 356ad03beeda1816747e95801379b7b7ba7c0ab8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771036"
---
# <a name="add-front-end-machine"></a>フロント エンド コンピューターの追加

このプールにフロント エンド サーバーとして追加する各コンピューターの完全修飾ドメイン名 (FQDN) を指定します。一覧にコンピューターを追加した後、トポロジを公開するまでの間はいつでも、コンピューターの FQDN を更新したり、プールからコンピューターを削除したりできます。トポロジの公開後に FQDN を変更するには、トポロジ ビルダーでサーバーを削除し、新しいサーバーを新しい FQDN でプールに追加する必要があります。トポロジへのフロント エンド プールの追加の詳細については、「展開」のドキュメントの「[Define and Configure a Front End Pool (フロント エンド プールの定義および構成)](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)」を参照してください。

> [!IMPORTANT]
> トポロジ ビルダーは、プール内に最大 20 台のフロント エンド サーバーを含め可能な点に注意してください。 サポートされるサーバーの最大数は 12 です。 ファブリックで定義できるステートフル サーバーは最大 20 台で、そのうち 12 台は一度にアクティブおよびオンラインにできます。