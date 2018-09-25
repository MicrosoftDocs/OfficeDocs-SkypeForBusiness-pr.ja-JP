---
title: マイクロソフトのチームとビジネス管理センターの Skype のチームを管理します。
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: 表示またはマイクロソフトのチームとビジネス管理センターの Skype で、チームを更新する方法について説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1dbfddf2f9cfba12943b8b2e18326de1877e1de3
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25018824"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a>マイクロソフトのチームとビジネス管理センターの Skype のチームを管理します。
==========================================

## <a name="overview"></a>概要

IT 管理者としては、表示または更新を組織が共同作業、またはを設定する各チームは、所有者のいないチームの所有者の割り当てなどの修復アクションを実行する必要がある必要があります。 ビジネス管理センターの Microsoft チームの PowerShell モジュールおよびマイクロソフトのチームと Skype 経由で使用するチームを管理することができます。 これら 2 つのツールセットを使用して、完全な管理機能には、次の役割の 1 つを割り当てられていることを確認の操作をする必要があります。

- グローバル ・ アドミニストレーター
- チーム サービス管理者

マイクロソフトのチームでの管理者の役割に関する詳細については、[ここでは](using-admin-roles.md)、詳細情報を参照および[コマンドレットのリファレンスをマイクロソフトのチーム](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps)のチームを管理するための PowerShell コマンドレットを使用する方法について。  

この資料では、マイクロソフトのチームとビジネス管理センターの Skype でのチームの管理ツールの概要について説明を提供します。

## <a name="teams-overview-grid"></a>チーム概要グリッド

チームの管理ツールは、マイクロソフトのチームと Skype ビジネス管理センターの [**チーム**] ノードの下。 (管理センターで、**チーム**を選択します > **チームを管理**します)。各チームは、Office 365 のグループでバックアップし、チームが有効になっている組織で Microsoft をされているすべてのグループをこのノードで表示します。

![チーム概要グリッド](media/manage-teams-in-modern-portal-image1.png)  

グリッドには、次のプロパティが表示されます。

- **チーム名**
- **チャネル**の既定の一般的なチャネルを含む、チーム内のすべてのチャネルの数です。
- **ユーザー**の所有者、来園者、および、テナントからのメンバーを含む、総ユーザー数のカウントです。
- **所有者**- このチームの所有者の数です。
- **来園者**がこのチームのメンバーである Azure Active Directory の B2B のゲスト ユーザーの数です。
- **プライバシー** - Office 365 のバックアップ グループの AccessType。

### <a name="search"></a>検索

検索は現在「を開始」の文字列をサポートしていると、**チーム名**フィールドを検索します。

### <a name="edit"></a>編集

グリッドからチームを選択し、[**編集**] ボタンでは、グループとチームに固有の設定を編集できます。

![チームを編集します。](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a>チーム プロファイル

チーム名をクリックすると、チームの主な概要グリッドから任意のチームのチームのプロファイル ページに移動できます。 メンバー、所有者、および来園者のチームに所属するチームのプロファイル ページを示しています (および O365 グループのバックアップを作成)、およびチームのチャネルとの設定。 チームのプロファイル] ページで、次の操作を実行できます。

- 追加またはメンバーとの所有者を削除します。
- 追加またはチャンネル (全般的なチャネルを削除することはできませんに注意してください) を削除します。
- チームを更新し、設定をグループ化します。
 
![チーム プロファイル](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a>チームを変更をします。

チームの次の要素を変更することができます。
- **チーム内のユーザー**の追加またはメンバーの削除、および昇格したり、所有者のレベルを下げる
- **チャネル**に新しいチャネルを追加または既存のチャンネルを削除できます。  デフォルトの「一般」チャネルを削除することはできませんし、1 回作成するチャネルの名前説明ではないのみを編集できます。
- **チーム名**
- **チームの説明**
- **チームの写真**
- **チームのプライバシー**がパブリックまたはプライベート
- **チームのクラス分け**に支えられて、Office 365 のグループの分類
- **チーム メンバーの設定**の選択のチーム メンバーの設定


チームに加えた変更が記録されます。 (名前、説明、写真、プライバシー、分類、またはチーム メンバーを変更する)、グループの設定を変更する場合これらの変更の原因は、監査のパイプラインを通過します。 チームに固有の設定に対するアクションを実行する場合、変更を追跡し、チームの全般的なチャネルの原因です。


## <a name="learn-more"></a>詳細情報

[マイクロソフト チーム コマンドレットのリファレンス](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps)  
[マイクロソフトのチームでの管理者の役割](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

