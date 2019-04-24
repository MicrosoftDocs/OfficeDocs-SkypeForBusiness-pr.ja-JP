---
title: Skype for Business Server 2015 での常設チャット管理者の作成
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: '概要: は、初期構成およびビジネス サーバー 2015 の Skype での永続的なチャット サービスの管理を有効にするのには永続的なチャット サーバー管理者ロールを作成する方法の詳細については、このトピックを読みます。'
ms.openlocfilehash: fb8a222f65f6fe579d3600df15a53bb84f65de66
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225343"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット管理者の作成
 
**の概要:** 初期構成およびビジネス サーバー 2015 の Skype での永続的なチャット サービスの管理を有効にするのには永続的なチャット サーバー管理者ロールを作成する方法の詳細については、このトピックを参照してください。
  
ビジネス サーバーの Skype は、特定のタスクを実行するユーザーを 1 つまたは複数の特定のグループのメンバーとして割り当てる必要があります。 ビジネス サーバー管理者の役割の定義済みの Skype ユーザーに割り当てることによって権限を付与する役割に基づくアクセス制御 (RBAC) が使用されます。 これらの役割は、Active Directory ドメイン サービスのユニバーサル セキュリティ グループに対応します。 、CsPersistentChatAdministrator、永続的なチャット管理者セキュリティ グループのメンバーは、永続的なチャット サーバーのコマンドレット、またはを使用してビジネス サーバー管理シェルの Skype、Skype ビジネスを実行することへのアクセスを許可は、サーバーのコントロール パネルです。
  
常設チャット サーバーを構成および管理する前に、適切なユーザー権限およびアクセス許可があること、および常設チャット管理者として活動するユーザーが常設チャット管理者セキュリティ グループに追加されていることを確認してください。
  
> [!NOTE] 
> 永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。 同じ機能は、チームで使用できます。 詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。 永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。

## <a name="create-a-persistent-chat-administrator"></a>Create a Persistent Chat administrator

CsPersistentChatAdministrator、永続的なチャット管理者セキュリティ グループにユーザーを追加するには、次の手順を実行します。
  
1. Active Directory グループのメンバーシップを変更できるアクセス許可を持つアカウントを使用して、Active Directory ユーザーおよびコンピューターがインストールされているコンピューターにログオンします。
    
2. [スタート]、[すべてのプログラム]、[管理ツール]、[Active Directory ユーザーとコンピューター] の順にクリックします。
    
3. [Active Directory ユーザーとコンピューター] で、自分のドメインの名前を展開し、[Users] コンテナーをクリックします。
    
4. セキュリティ グループの [CsPersistentChatAdministrator] を右クリックし、[プロパティ] をクリックします。
    
5. [プロパティ] ダイアログ ボックスの [メンバー] タブで、[追加] をクリックします。
    
6. [ユーザー、コンピューター、連絡先、またはグループの選択] ダイアログ ボックスの [選択するオブジェクト名を入力してください] ボックスに、グループに追加するユーザーの名前または表示名を入力し、[OK] をクリックします。
    
7. [プロパティ] ダイアログ ボックスで [OK] をクリックします。
    

