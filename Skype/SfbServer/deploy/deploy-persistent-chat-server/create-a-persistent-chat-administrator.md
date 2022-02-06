---
title: 2015 年に常設チャット管理者をSkype for Business Serverする
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: '概要: 常設チャット サーバー管理者の役割を作成して、2015 年に常設チャット サービスの初期構成と管理を有効にする方法については、このトピックSkype for Business Serverしてください。'
---

# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>2015 年に常設チャット管理者をSkype for Business Serverする
 
**概要:** このトピックでは、常設チャット サーバー管理者の役割を作成して、2015 年に常設チャット サービスの初期構成と管理を有効にする方法Skype for Business Serverしてください。
  
このSkype for Business Server、特定のタスクを実行するユーザーは、1 つ以上の特定のグループのメンバーとして割り当てる必要があります。 Role-Basedアクセス制御 (RBAC) を使用して、ユーザーを定義済みの管理者ロールに割り当Skype for Business Server付与します。 これらの役割は、Active Directory ドメイン サービスのユニバーサル セキュリティ グループに対応します。 常設チャット管理者セキュリティ グループ CsPersistentChatAdministrator のメンバーには、Skype for Business Server 管理シェルまたは Skype for Business Server コントロール パネルを使用して実行できる常設チャット サーバー コマンドレットへのアクセス権が付与されます。
  
常設チャット サーバーを構成および管理する前に、適切なユーザー権限とアクセス許可が設定され、常設チャット管理者として機能するユーザーが常設チャット管理者セキュリティ グループに追加されます。
  
> [!NOTE] 
> 常設チャットは 2015 Skype for Business Serverで使用できますが、2019 年Skype for Business Serverではサポートされていません。 同じ機能は、Teams。 詳細については、「アップグレードの開始[方法」をMicrosoft Teamsしてください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、2015 年Skype for Business Serverします。

## <a name="create-a-persistent-chat-administrator"></a>常設チャット管理者の作成

常設チャット管理者セキュリティ グループ CsPersistentChatAdministrator にユーザーを追加するには、次の手順を実行します。
  
1. Active Directory グループのメンバーシップを変更するアクセス許可を持つアカウントを使用して、Active Directory ユーザーとコンピューターがインストールされているコンピューターにログオンします。
    
2. [スタート] をクリックし、[すべてのプログラム] をクリックし、[管理ツール] をクリックし、[Active Directory ユーザーおよびコンピューター] をクリックします。
    
3. Active Directory ユーザーおよびコンピューターで、自分のドメインの名前を展開し、[Users] コンテナーをクリックします。
    
4. セキュリティ グループ CsPersistentChatAdministrator を右クリックし、[プロパティ] をクリックします。
    
5. [プロパティ] ダイアログ ボックスの [メンバー] タブで、[追加] をクリックします。
    
6. [ユーザー、コンピューター、連絡先、またはグループの選択] ダイアログ ボックスで、[選択するオブジェクト名を入力する] ボックスにグループに追加するユーザーのユーザー名または表示名を入力し、[OK] をクリックします。
    
7. [プロパティ] ダイアログ ボックスで [OK] をクリックします。
    

