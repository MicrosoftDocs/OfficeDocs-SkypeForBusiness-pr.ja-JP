---
title: Skype for Business Server 2015 での常設チャット管理者の作成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: '概要: このトピックでは、常設チャット サーバー管理者の役割を作成して、Skype for Business Server 2015 で常設チャット サービスの初期構成と管理を有効にする方法について説明します。'
ms.openlocfilehash: eea989b0284353e193ebf99a0be99b2d0811e532
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802097"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット管理者の作成
 
**概要:** このトピックでは、Skype for Business Server 2015 で常設チャット サービスの初期構成と管理を有効にする常設チャット サーバー管理者の役割を作成する方法について説明します。
  
Skype for Business Server では、特定のタスクを実行するユーザーを 1 つ以上の特定のグループのメンバーとして割り当てる必要があります。 Role-Basedアクセス制御 (RBAC) は、定義済みの Skype for Business Server 管理者の役割にユーザーを割り当て、特権を付与するために使用されます。 これらの役割は、Active Directory ドメイン サービスのユニバーサル セキュリティ グループに対応しています。 常設チャット管理者セキュリティ グループ CsPersistentChatAdministrator のメンバーには、Skype for Business Server 管理シェルまたは Skype for Business Server コントロール パネルを使用して実行できる常設チャット サーバー コマンドレットへのアクセス権が付与されます。
  
常設チャット サーバーを構成および管理する前に、適切なユーザー権限とアクセス許可が設定され、常設チャット管理者として機能するユーザーが常設チャット管理者セキュリティ グループに追加されます。
  
> [!NOTE] 
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。

## <a name="create-a-persistent-chat-administrator"></a>常設チャット管理者の作成

常設チャット管理者セキュリティ グループ CsPersistentChatAdministrator にユーザーを追加するには、次の手順を実行します。
  
1. Active Directory グループのメンバーシップを変更するアクセス許可を持つアカウントを使用して、Active Directory ユーザーとコンピューターがインストールされているコンピューターにログオンします。
    
2. [スタート] をクリックし、[すべてのプログラム] をクリックし、[管理ツール] をクリックし、[Active Directory ユーザーおよびコンピューター] をクリックします。
    
3. Active Directory ユーザーおよびコンピューターで、自分のドメインの名前を展開し、[Users] コンテナーをクリックします。
    
4. セキュリティ グループ CsPersistentChatAdministrator を右クリックし、[プロパティ] をクリックします。
    
5. [プロパティ] ダイアログ ボックスの [メンバー] タブで、[追加] をクリックします。
    
6. [ユーザー、コンピューター、連絡先、またはグループの選択] ダイアログ ボックスで、グループに追加するユーザーのユーザー名または表示名を [選択するオブジェクト名を入力してください] ボックスに入力し、[OK] をクリックします。
    
7. [プロパティ] ダイアログ ボックスで [OK] をクリックします。
    

