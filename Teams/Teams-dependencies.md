---
title: "Microsoft のチームでゲスト アクセスを承認します。"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
description: "Microsoft チーム ゲスト アクセス機能と承認の 4 つの異なるレベルの機能を管理します。"
ms.openlocfilehash: 86384a18fdea3d15bfb0bf6368a2529a05872371
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="authorize-guest-access-in-microsoft-teams"></a>Microsoft のチームでゲスト アクセスを承認します。
===========================================

組織の要件を満たすためには、Microsoft チーム ゲスト アクセス機能と承認の 4 つの異なるレベルの機能を管理できます。すべての承認レベルは、Office 365 テナントに適用されます。各承認レベルは、次に示すように、ゲスト エクスペリエンスを制御します。
- **Azure Active Directory**: Microsoft チームでゲスト アクセス Azure AD ビジネス基幹業務 (B2B) プラットフォームに依存します。ディレクトリ、テナント、およびアプリケーション レベルでのゲスト ユーザー エクスペリエンスを制御します。 
- **Microsoft チーム**: のみ Microsoft チームを制御します。 
- **Office 365 のグループ**: Office 365 のグループおよび Microsoft チーム ゲスト エクスペリエンスを制御します。
- **SharePoint Online と OneDrive for Business**: ゲストでの操作環境、SharePoint Online、OneDrive for Business、Office 365 のグループ、および Microsoft チームを制御します。

別の承認、次のレベルは、セットアップする方法のゲスト アクセス、組織の柔軟性を提供します。たとえば、Microsoft チーム組織のゲスト ユーザーを許可しない場合は、アクセスだけを無効にゲスト Microsoft チームでします。別の例: AAD、チーム、グループ レベルでゲスト アクセスを有効にできますが、[選択したデータの分類などの 1 つまたは複数の条件を満たすチームで無効にするゲスト ユーザーの追加と値が等しい機密します。またなど、Office 365 グループを使用しません。SharePoint Online と OneDrive for Business、Office 365 のグループに依存しないする独自のゲスト アクセスの設定をあります。 

> [!NOTE]
> ゲストは、 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347)と[Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019)サービスの制限の適用対象はします。 

  次の図では、ゲスト アクセス承認の依存関係が与えられてし、Azure Active Directory、マイクロソフトのチームと Office 365 の統合方法を示します。


![ゲスト アクセスの承認の依存関係の図。](media/teams_dependencies_image1.png)


##<a name="azure-active-directory"></a>Azure Active Directory

Azure AD ビジネス基幹業務 (B2B) の共同作業の潜在的なゲスト ユーザーへの招待を送信していないテナント管理者に制限されています。代わりに、委任ロールを持つができるように招待状を送信するのにユーザーを招待状を送信するには、ポリシーを使用することができます。

招待状の設定は、テナント レベルで適用し、ディレクトリ、テナント、およびアプリケーション レベルでのゲスト ユーザー エクスペリエンスを制御します。


![Azure Active Directory ポータルのスクリーン ショットのユーザー設定します。](media/teams_dependencies_image2.png)


次の招待状のポリシーを設定できます。
- 招待状をオフにします。
- 管理者とゲスト招待者の役割のユーザーのみを招待できます。
- 管理者、ゲスト招待者の役割およびメンバーを招待できます。
- ゲストを含む、すべてのユーザーを招待できます。(これは、テナントの既定のポリシーです)。


##<a name="microsoft-teams"></a>Microsoft チーム

Microsoft チームで、ゲスト エクスペリエンスが有効か無効か、組織を制御できます。設定は、既定で無効にし、Microsoft チームのみテナント レベルで適用します。



Office 365 管理センターから Microsoft チーム ゲスト アクセスの設定を管理できます。詳細については、 [Microsoft チームにゲスト アクセスを無効または有効にする](set-up-guests.md)を参照してください。 


##<a name="office-365-groups"></a>Office 365 のグループ

Office 365 のグループから、組織内には、ゲスト ユーザーの追加とすべての Office 365 のグループおよび Microsoft チームにゲスト アクセスを制御できます。

1. [Https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)での自分の Office 365 グローバル管理者アカウントでサインインします。
    
  
2. ナビゲーション メニューで、**設定**を選択し、[**サービス&amp;アドイン**します。
    
  
3. **Office 365 グループ**を選択します。
    
     ![Office 365 のグループ](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. [Office 365 のグループ] ページで、設定に切り替えますの**オン**と**オフを切り替える**、によっては、組織の Office 365 へのアクセス グループ外チーム、グループの所有者ができるようにする場合。をクリックするか、 **[** **グループに所属組織外の人を追加するグループ所有者**の横にあるトグルをタップします。この切り替えを有効にする場合に、組織外のユーザーを Office 365 のグループに追加するグループとチームの所有者ができるようにして、チームが Microsoft かどうかは、コントロールに別のオプションが表示されます。ゲスト ユーザーの追加] グループおよびチームの所有者ができるようにする場合、この切り替え上に設定します。![スクリーン ショットは、グループ コンテンツには、組織のアクセスの外側のグループのメンバーができるようにして、組織外のユーザーをグループに追加するグループの所有者をオンにするオプションを使用して、Office 365 グループ パネルを示しています。](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)




上記の設定は、テナント レベルで適用し、Office 365 のグループおよび Microsoft チーム ゲスト エクスペリエンスを制御します。


##<a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online と OneDrive for Business

チームは、SharePoint Online と OneDrive for Business にファイルやチャネルおよびチャットのドキュメントの保存に依存します。  
  
    
    
エクスペリエンスを可能に、完全なチーム ゲスト アクセス、Office 365 の管理者は**、次の設定をオン**に必要があります。
  
    
    

- SharePoint Online: を**のみディレクトリ内にある外部ユーザーとの共有を許可します。**
    
    詳細については、 [SharePoint Online 環境の外部共有を管理する](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85)を参照してください。
    
  
- Office 365 のグループ:**グループの所有者グループに所属組織外の人を追加します。**
    
    詳細については、 [Microsoft チームへのゲスト アクセスの制御](#controlguest)を参照してください。
  

上記の設定は、テナント レベルで適用し、SharePoint Online、OneDrive for Business、Office 365 のグループと Microsoft チームのゲスト エクスペリエンスを制御します。


チーム接続されているチーム サイトの SharePoint Online の外部のユーザー設定を管理することができます。詳細については、 [SharePoint チーム サイトの設定を管理する](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)を参照してください。