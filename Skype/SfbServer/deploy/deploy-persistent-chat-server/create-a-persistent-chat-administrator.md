---
title: Skype for Business Server 2015 での常設チャット管理者の作成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: '概要: このトピックでは、Skype for Business Server 2015 で常設チャットサービスの初期構成と管理を有効にするための、常設チャットサーバー管理者の役割を作成する方法について説明します。'
ms.openlocfilehash: 1b593f1de776f1896d43bab35a15af7b6bcf7245
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273883"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット管理者の作成
 
**概要:** このトピックでは、Skype for Business Server 2015 の常設チャットサービスの初期構成と管理を有効にするための、常設チャットサーバー管理者の役割を作成する方法について説明します。
  
Skype for Business Server では、特定のタスクを実行するユーザーは、1つ以上の特定のグループのメンバーとして割り当てる必要があります。 ロールベースのアクセス制御 (RBAC) を使用して、事前定義された Skype for Business Server の管理者ロールにユーザーを割り当てることによって特権を付与します。 これらの役割は、Active Directory ドメイン サービスのユニバーサル セキュリティ グループに対応します。 常設チャット管理者セキュリティグループ CsPersistentChatAdministrator のメンバーには、Skype for Business Server 管理シェルまたは Skype for Business を使用して実行できる常設チャットサーバーコマンドレットへのアクセスが許可されます。サーバーコントロールパネル。
  
常設チャット サーバーを構成および管理する前に、適切なユーザー権限およびアクセス許可があること、および常設チャット管理者として活動するユーザーが常設チャット管理者セキュリティ グループに追加されていることを確認してください。
  
> [!NOTE] 
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「 [Skype For business から Microsoft Teams への旅](/microsoftteams/journey-skypeforbusiness-teams)」を参照してください。 常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。

## <a name="create-a-persistent-chat-administrator"></a>Create a Persistent Chat administrator

常設チャット管理者セキュリティグループ CsPersistentChatAdministrator にユーザーを追加するには、次の手順を実行します。
  
1. Active Directory グループのメンバーシップを変更できるアクセス許可を持つアカウントを使用して、Active Directory ユーザーおよびコンピューターがインストールされているコンピューターにログオンします。
    
2. [スタート]、[すべてのプログラム]、[管理ツール]、[Active Directory ユーザーとコンピューター] の順にクリックします。
    
3. [Active Directory ユーザーとコンピューター] で、自分のドメインの名前を展開し、[Users] コンテナーをクリックします。
    
4. セキュリティ グループの [CsPersistentChatAdministrator] を右クリックし、[プロパティ] をクリックします。
    
5. [プロパティ] ダイアログ ボックスの [メンバー] タブで、[追加] をクリックします。
    
6. [ユーザー、コンピューター、連絡先、またはグループの選択] ダイアログ ボックスの [選択するオブジェクト名を入力してください] ボックスに、グループに追加するユーザーの名前または表示名を入力し、[OK] をクリックします。
    
7. [プロパティ] ダイアログ ボックスで [OK] をクリックします。
    

