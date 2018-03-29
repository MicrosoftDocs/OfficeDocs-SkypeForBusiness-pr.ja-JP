---
title: 常設チャットのファイル ストアの追加
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Standard Edition サーバーまたは Enterprise Edition フロントエンド プールのファイル ストアとして使用するファイル共有を指定する必要があります。既存のファイル共有をファイル ストアに使用できます。または、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。
ms.openlocfilehash: 76b116d469bf6369174815d6b396a64149518f17
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-file-store"></a>常設チャットのファイル ストアの追加
 
Standard Edition サーバーまたは Enterprise Edition フロントエンド プールのファイル ストアとして使用するファイル共有を指定する必要があります。既存のファイル共有をファイル ストアに使用できます。または、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。
  
> [!IMPORTANT]
> Skype ビジネス サーバー用のファイル共有は、エンタープライズ版フロント エンド サーバーに配置することはできませんが、Standard Edition サーバーに配置することができます。 
  
> [!IMPORTANT]
> ファイル共有を作成する前にトポロジ ビルダーでファイル共有を定義できますが、トポロジを公開する前に定義する定義済みの場所にファイル共有を作成する必要があります。 
  
> [!IMPORTANT]
> 永続的なチャット サーバーを追加するか、永続的なチャットのサーバー プールのトポロジでは、トポロジ ビルダーには、ファイルを設定できる必要がありますを格納し、随意アクセス制御を構成するファイル ストアに使用するファイル共有のリスト (Dacl) を設定します。 そのため、トポロジ ビルダーを実行して新しいトポロジを公開するときに、サイト共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログインする必要があります。 
  
## <a name="see-also"></a>関連項目

#### 

[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[ビジネス サーバー 2015 トポロジの場合、Skype に永続的なチャット サーバーを追加します。](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーのハードウェアおよびソフトウェアの要件](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[ビジネス サーバー 2015 の Skype のサーバーの要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[ビジネス サーバー 2015 の Skype のトポロジーの基本事項](../../plan-your-deployment/topology-basics/topology-basics.md)

