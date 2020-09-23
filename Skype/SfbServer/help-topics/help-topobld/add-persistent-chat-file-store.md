---
title: 常設チャットのファイル ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Standard Edition サーバーまたは Enterprise Edition フロント エンドのプールのファイル ストアとして使用するファイル共有を指定する必要があります。既存のファイル共有をファイル ストアに使用できます。または、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。
ms.openlocfilehash: 76169673848d9cbace41642d5058bfb60e90508a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218678"
---
# <a name="add-persistent-chat-file-store"></a>常設チャットのファイル ストアの追加
 
Standard Edition サーバーまたは Enterprise Edition フロント エンドのプールのファイル ストアとして使用するファイル共有を指定する必要があります。既存のファイル共有をファイル ストアに使用できます。または、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。
  
> [!IMPORTANT]
> Skype for Business Server のファイル共有は、Enterprise Edition フロントエンドサーバーに配置することはできませんが、Standard Edition サーバーに配置することはできます。 
  
> [!IMPORTANT]
> ファイル共有を作成する前にトポロジ ビルダーでファイル共有を定義できますが、トポロジを公開する前に定義する定義済みの場所にファイル共有を作成する必要があります。 
  
> [!IMPORTANT]
> 常設チャットサーバーまたは常設チャットサーバープールをトポロジに追加するには、トポロジビルダーでファイルストアをセットアップし、ファイルストアに使用するファイル共有に随意アクセス制御リスト (Dacl) を構成できる必要があります。 これには、トポロジ ビルダーを実行して新しいトポロジを公開するときに、サイト共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログインする必要があります。 
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 での常設チャットサーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[常設チャットサーバーを Skype for Business Server 2015 トポロジに追加する](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Skype for Business Server 2015 の常設チャットサーバーのハードウェアおよびソフトウェア要件](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Skype for Business Server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 のトポロジの基本](../../plan-your-deployment/topology-basics/topology-basics.md)
