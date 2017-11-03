---
title: "Microsoft Teams での Office 365 の依存関係"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Microsoft Teams は Office 365 グループ、SharePoint Online、および OneDrive for Business を利用します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: e04770535976f509a8ac16cf054ea5e6760b5231
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
<a name="office-365-dependencies-for-microsoft-teams"></a>Microsoft Teams での Office 365 の依存関係
===========================================

Microsoft Teams は、Office 365 グループを利用して、チームのメンバーシップやチームのデータ分類設定などのその他のプロパティを保管します。 Office 365 グループは、SharePoint サイトや Power BI ダッシュボードなどの一連の共有チーム資産を利用するために、クロス アプリケーションのメンバーシップを提供し、チームが効果的かつ安全にコラボレーションできるようにするサービスです。 

Teams は、SharePoint Online と OneDrive for Business も利用して、チャネルとチャット会話のファイルやドキュメントを保管します。 さらに、Teams は、Office 365 グループを利用して、チームのメンバーシップやチームのデータ分類設定などのその他のプロパティを保管します。 ゲストにも [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) と [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) のサービスの制限が適用されます。
  
    
    
Teams のゲスト アクセスの完全な操作性を有効にするため、Office 365 管理者は次の設定を**オン**にする必要があります。
  
    
    

- SharePoint Online: **Only allow sharing with external users already in the directory (ディレクトリに既に存在する外部ユーザーのみとの共有を許可する)**
    
    詳しくは、「[SharePoint Online 環境の外部共有を管理する](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85)」をご覧ください。
    
  
- Office 365 グループ: **Let group owners add people outside the organization to groups (グループ所有者に組織外のユーザーをグループに追加させる)**
    
    詳細については、「[Control guest access to Microsoft Teams (Microsoft Teams へのゲスト アクセスを制御する)](#controlguest)」をご覧ください。
  

Teams で接続したチーム サイトの SharePoint Online 外部ユーザー設定を管理できます。 詳細については、「[SharePoint チーム サイト設定を管理する](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)」をご覧ください。