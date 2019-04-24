---
title: 残りのユーザーの移動
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'ビジネス サーバー 2019 展開新しい Skype にユーザーを移動するには、ビジネス サーバーのコントロール パネルまたは Skype のビジネス サーバー管理シェルのいずれかの Skype を使用します。 ビジネス サーバー 2019 の Skype へのスムーズな移行を確実にいくつかの要件を満たす必要があります。 このトピックの手順を完了するための前提条件についての詳細は、移行のためのクライアントを構成するを参照してください。 ユーザーの移動に関する詳細な手順については、フェーズ 4 を参照してください: パイロット プールにテスト ユーザーを移動します。'
ms.openlocfilehash: 9f984b7fac919decce521c6dafc587a4ac86de50
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231589"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Skype をビジネス サーバー 2019 の残りのユーザーを移動します。

ビジネス サーバー 2019 展開新しい Skype にユーザーを移動するには、ビジネス サーバーのコントロール パネルまたは Skype のビジネス サーバー管理シェルのいずれかの Skype を使用します。 ビジネス サーバー 2019 の Skype へのスムーズな移行を確実にいくつかの要件を満たす必要があります。 このトピックの手順を完了するための前提条件についての詳細は、[移行のためのクライアントを構成する](configure-clients-for-migration.md)を参照してください。 ユーザーの移動に関する詳細な手順についてを参照してください[フェーズ 4: パイロット プールにテスト ユーザーの移動](phase-4-move-test-users-to-the-pilot-pool.md)。
  
> [!IMPORTANT]
> ビジネス サーバー 2019 の Skype を従来の環境からユーザーを移動する、Active Directory ユーザーとコンピューター スナップインまたは従来の管理ツールを使うことはできません。 
  
Skype のビジネス サーバー 2019 プールにユーザーを移動すると、ユーザーのデータは、新しいプールに関連付けられているバックエンド ・ データベースに移動されます。 
  
> [!IMPORTANT]
> これには、従来のユーザーによって作成されたアクティブな会議が含まれます。 などの従来のユーザーが**自分の会議**の会議を設定している場合その会議、できるビジネス サーバー 2019 プールの新しい Skype のユーザーを移動した後。 その会議にアクセスするための詳細では、同じ**会議 URL および会議 ID**は使用できます。 唯一の違いは、ビジネス サーバー 2019 プールの場合は、Skype では、従来のプールではなく、会議がここでホストされています。 
  
> [!NOTE]
> ビジネス サーバー 2019 は同時にアップグレードされたクライアントを展開するは、Skype のユーザーを格納します。 新機能は、新しいクライアント ソフトウェアにアップグレードする場合にのみユーザーが利用されます。 
  
### <a name="post-migration-task"></a>ポスト移行タスク

1. ユーザーを移動した後は、それらに割り当てられている会議ポリシーを確認します。 
    
2. によってユーザーが開催する会議が置かれている Skype レガシー インストールのホームは、フェデレーション ユーザーとシームレスにビジネス サーバー 2019 作業のためには、移行したユーザーに割り当てられている会議ポリシーは、匿名の参加者を許可する必要があります。
    
3. 匿名の参加者**に匿名ユーザーを招待する参加者を許可する**ビジネス サーバー 2019 のコントロール パネルの Skype で選択されているし、 **AllowAnonymousParticipantsInMeetings**を許可する会議ポリシーの設定を**True**にしますビジネス サーバー管理シェルには、Skype で**Get CsConferencingPolicy**コマンドレットから出力します。 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

