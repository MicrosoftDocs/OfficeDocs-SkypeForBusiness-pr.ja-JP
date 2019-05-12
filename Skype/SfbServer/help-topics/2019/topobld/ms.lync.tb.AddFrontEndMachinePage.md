---
title: フロントエンド コンピューターの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: このプール内のフロント エンド サーバーとして追加する各コンピューターの完全修飾ドメイン名 (FQDN) を指定します。 一覧にコンピューターを追加した後でも、トポロジを公開するまでの間は、いつでもコンピューターの FQDN を更新したり、プールからコンピューターを削除したりできます。 トポロジ ビルダーでは、サーバーを削除し、新しい FQDN を持つプールに新しいサーバーを追加、トポロジを公開すると、FQDN を変更する必要です。 トポロジにフロント エンド プールを追加する方法の詳細を定義して構成するフロント エンド プールを展開に関するドキュメントを参照してください。
ms.openlocfilehash: 321e1f392fb06ba4e99dc17e668e188b2fee5338
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33912065"
---
# <a name="add-front-end-machine"></a>フロントエンド コンピューターの追加

このプール内のフロント エンド サーバーとして追加する各コンピューターの完全修飾ドメイン名 (FQDN) を指定します。 一覧にコンピューターを追加した後でも、トポロジを公開するまでの間は、いつでもコンピューターの FQDN を更新したり、プールからコンピューターを削除したりできます。 トポロジ ビルダーでは、サーバーを削除し、新しい FQDN を持つプールに新しいサーバーを追加、トポロジを公開すると、FQDN を変更する必要です。 トポロジにフロント エンド プールを追加する方法の詳細は、展開に関するドキュメントの[定義およびフロント エンド プールを構成する](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)を参照してください。

> [!IMPORTANT]
> トポロジ ビルダーがプール内に最大 20 個のフロント エンド サーバーを持つことができることを示しているに注意してください。 サーバーの最大許容数は 12 です。 うち 12 でき、アクティブなオンライン同時に、ファブリック内で定義されている最大 20 個のステートフル サーバーを持つことができます。


