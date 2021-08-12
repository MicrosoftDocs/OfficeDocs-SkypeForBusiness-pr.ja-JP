---
title: フロントエンド コンピューターを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: このプールにフロント エンド サーバーとして追加する各コンピューターの完全修飾ドメイン名 (FQDN) を指定します。一覧にコンピューターを追加した後、トポロジを公開するまでの間はいつでも、コンピューターの FQDN を更新したり、プールからコンピューターを削除したりできます。トポロジの公開後に FQDN を変更するには、トポロジ ビルダーでサーバーを削除し、新しいサーバーを新しい FQDN でプールに追加する必要があります。トポロジへのフロント エンド プールの追加の詳細については、「展開」のドキュメントの「Define and Configure a Front End Pool (フロント エンド プールの定義および構成)」を参照してください。
ms.openlocfilehash: 2105f316edc6a73d2758a5824028b4cc9b177a2be283e0665a836872656b7e17
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54311875"
---
# <a name="add-front-end-machine"></a>フロント エンド コンピューターの追加

このプールにフロント エンド サーバーとして追加する各コンピューターの完全修飾ドメイン名 (FQDN) を指定します。一覧にコンピューターを追加した後、トポロジを公開するまでの間はいつでも、コンピューターの FQDN を更新したり、プールからコンピューターを削除したりできます。トポロジの公開後に FQDN を変更するには、トポロジ ビルダーでサーバーを削除し、新しいサーバーを新しい FQDN でプールに追加する必要があります。トポロジへのフロント エンド プールの追加の詳細については、「展開」のドキュメントの「[Define and Configure a Front End Pool (フロント エンド プールの定義および構成)](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)」を参照してください。

> [!IMPORTANT]
> トポロジ ビルダーは、プール内に最大 20 台のフロント エンド サーバーを含め可能な点に注意してください。 サポートされるサーバーの最大数は 12 です。 ファブリックで定義できるステートフル サーバーは最大 20 台で、そのうち 12 台は一度にアクティブおよびオンラインにできます。