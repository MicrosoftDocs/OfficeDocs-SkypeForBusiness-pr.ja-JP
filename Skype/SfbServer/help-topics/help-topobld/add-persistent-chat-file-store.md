---
title: 常設チャット ファイル ストアの追加
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 83c88710e288fb2282950c2c9cc3922a65cef63bedbc57537dd01b5634feb7e5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307358"
---
# <a name="add-persistent-chat-file-store"></a>常設チャット ファイル ストアの追加
 
Standard Edition サーバーまたは Enterprise Edition フロント エンドのプールのファイル ストアとして使用するファイル共有を指定する必要があります。既存のファイル共有をファイル ストアに使用できます。または、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。
  
> [!IMPORTANT]
> サーバーのファイル共有Skype for Business Serverフロント エンド サーバー上Enterprise Editionすることはできませんが、サーバー上にStandard Editionできます。 
  
> [!IMPORTANT]
> ファイル共有を作成する前にトポロジ ビルダーでファイル共有を定義できますが、トポロジを公開する前に定義する定義済みの場所にファイル共有を作成する必要があります。 
  
> [!IMPORTANT]
> 常設チャット サーバーまたは常設チャット サーバー プールをトポロジに追加する場合、トポロジ ビルダーはファイル ストアをセットアップし、ファイル ストアに使用するファイル共有上の任意のアクセス制御リスト (DACLs) を構成できる必要があります。 これには、トポロジ ビルダーを実行して新しいトポロジを公開するときに、サイト共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログインする必要があります。 
  
## <a name="see-also"></a>関連項目

[2015 年の常設チャット サーバー Skype for Business Serverする](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[常設チャット サーバーを 2015 Skype for Business Serverトポロジに追加する](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[2015 年の常設チャット サーバーのハードウェア要件とソフトウェア要件Skype for Business Server](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[2015 年のサーバー Skype for Business Server要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[トポロジ 2015 Skype for Business Serverの基本](../../plan-your-deployment/topology-basics/topology-basics.md)
