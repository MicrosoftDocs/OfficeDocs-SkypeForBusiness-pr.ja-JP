---
title: Microsoft Teams でのゲスト エクスペリエンス
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: この記事では、ゲストが利用できる Microsoft Teams の機能性について説明します。
ms.openlocfilehash: 5d8bb9ab670da0a4002f69cf5ddec9f245cd9c13
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2022
ms.locfileid: "62190698"
---
# <a name="guest-experience-in-teams"></a>Teams でのゲスト エクスペリエンス

ゲストがチームに参加するように招待されると、「ようこそ」メール メッセージが届きます。 このメッセージには、チームに関するいくつかの情報と、メンバーとして想定されることが記載されています。 ゲストは、チームとそのチャネルにアクセスする前に、メール メッセージで **[Microsoft Teams を開く]** を選択して、招待を承諾する必要があります。
    
![ようこそメール メッセージの例を示すスクリーンショット。](media/guest-experience-image1.png)
    
すべてのチーム メンバーは、チーム所有者がゲストを追加した旨およびそのゲストの名前を知らせるメッセージを確認することができます。 チームのメンバー全員がゲストが誰であるかを簡単に判断できます。 チャネル スレッドの右上隅にあるタグは、チームのゲストの数を示し、 (**ゲスト**) ラベルが各ゲストの名前の横に表示されます。

![チームのゲスト数を示すタグを示すスクリーンショット。](media/guest-experience-image2.png)

Teams でのゲストエクスペリエンスに関する次のビデオをご確認ください。
- [ゲストとしてTeams会議に参加する](https://support.microsoft.com/office/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4)
- [会議で外部ゲストとTeamsする](https://support.microsoft.com/office/work-with-external-guests-180ed260-d3ef-4247-9f24-1984fc76d5f0)

## <a name="comparison-of-team-member-and-guest-capabilities"></a>チーム メンバーとゲスト機能の比較

次の表は、組織のチーム メンバーが利用できる Teams の機能と、ゲストが利用できる Teams の機能を比較したものです。 Teams の管理者は、ゲストが利用できる機能を制御します。

| Teams の機能 | 組織の Teams ユーザー | Guest |
|:-----|:-----|:-----|
|チャネルの作成  <br/>  *この機能はチーム所有者によって制御されます。*  <br/> |&#x2713;|&#x2713;|
|プライベート チャットに参加する  <br/> |&#x2713;|&#x2713;|
|チャネルの会話に参加する  <br/> |&#x2713;|&#x2713;|
|メッセージを投稿、削除、編集する  <br/> |&#x2713;|&#x2713;|
|チャネル ファイルを共有する  <br/> |&#x2713;|&#x2713;|
|SharePoint ファイルにアクセスする<br/> |&#x2713;|&#x2713;|
|ファイルの添付<br/> |&#x2713;|チャネルの投稿のみ|
|プライベート チャットファイルをダウンロードする<br/> |&#x2713;|&#x2713;|
|ファイル内で検索する<br/> |&#x2713;||
|チャット ファイルを共有する  <br/> |&#x2713;||
|アプリ (タブ、ボット、コネクタ) を追加する  <br/> |&#x2713;||
|会議を作成またはスケジュールにアクセスする  <br/> |&#x2713;||
|OneDrive for Business ストレージにアクセスする  <br/> |&#x2713;||
|テナント全体およびチーム/チャネルのゲスト アクセス ポリシーを作成する  <br/> |&#x2713;||
|Microsoft 365 または Office 365 組織のドメイン外のユーザーを招待する <br/>  *この機能はチーム所有者によって制御されます。*  <br/> <br/> |&#x2713;||
|チームを作成する  <br/> |&#x2713;||
|パブリック チームを検出して参加する  <br/> |&#x2713;||
|組織図を表示する  <br/> |&#x2713;||
|インライン翻訳を使用する  <br/> |&#x2713;||
|チーム所有者になる  <br/> |&#x2713;||

次の表は、ゲストが利用できる通話機能と会議機能を示しており、他の種類のユーザーと比較しています。

| 通話機能 | ゲスト | E1 および E3 ユーザー | E5 およびエンタープライズ VoIP ユーザー |
| --------------- | ----- | -------------- | -------------- |
| VOIP 通話 | はい | Yes | Yes |
| グループ通話 | はい | Yes | Yes |
| 通話の重要なコントロール (保留、ミュート、ビデオのオン/オフ、画面共有) のサポート | はい | Yes | Yes |
| 転送先 | はい | Yes | Yes |
| 通話を転送する | はい | Yes | Yes |
| 取次転送をする | はい | Yes | Yes |
| その他のユーザーを VOIP を介して通話に追加する | はい | Yes | Yes |
| 電話番号でユーザーを通話に追加する | いいえ | いいえ | Yes |
| 着信転送ターゲット | いいえ | Yes | Yes |
| 通話グループ ターゲット | いいえ | Yes | Yes |
| 応答しなかったターゲット | いいえ | Yes | Yes |
| フェデレーション通話のターゲットとなる | いいえ | Yes | Yes |
| フェデレーション通話を発信する | いいえ | Yes | Yes |
| 通話を即時転送する | いいえ | いいえ | Yes |
| 複数の通話の呼び出しを同時に行う | いいえ | いいえ | Yes |
| 応答しなかった通話をルーティングする | いいえ | いいえ | Yes |
| 不在着信をボイスメールに移動する | いいえ | いいえ<sup>1</sup> |はい |
| 通話を受信できる電話番号を持つ | いいえ | いいえ | Yes |
| 電話番号をダイヤルする | いいえ | いいえ | Yes |
| 通話設定にアクセスする | いいえ | いいえ | Yes |
| ボイスメールの挨拶を変更する | いいえ | いいえ<sup>1</sup> | はい |
| 着信音を変更する | いいえ | いいえ  | はい |
| TTY のサポート | いいえ | いいえ | はい |
| 代理人を利用する | いいえ | いいえ | Yes |
|  代理人となる | いいえ | いいえ | Yes |

<sup>1</sup> この機能は近日中に利用できるようになります。

> [!NOTE]
> Azure Active Directory (Azure AD) の **ゲスト ユーザー アクセス制限ポリシー** によって、ディレクトリ内のゲストのアクセス許可が決まります。 3 つのポリシー オプションがあります。
>  - **ゲスト ユーザーは、メンバーと同じアクセス権が与えられています (最も包括的)** 設定とは、ディレクトリ内の通常のユーザーと同様にディレクトリ データへのアクセス権があることを意味します。
>  - **ゲストユーザーが、ディレクトリ オブジェクトのプロパティとメンバーシップに制限付きアクセスがある** 設定は、ユーザー、グループ、または Microsoft Graph を使用して他のディレクトリリソースを列挙するなど、特定のディレクトリタスクのアクセス許可がゲストに与えられていないことを意味します。
>  - **Guest ユーザーのアクセスは、自分のディレクトリ オブジェクトのプロパティとメンバーシップ に制限がある (最も制限の厳しい)** 設定は、ゲスト自身のディレクトリ オブジェクトにのみアクセスできます。
>
>詳細については、[「Azure Active Directory でのユーザーの既定のアクセス許可とは」](/azure/active-directory/fundamentals/users-default-permissions)を参照してください。

## <a name="related-topics"></a>関連項目

[ゲスト ユーザーとして組織を脱退する](/azure/active-directory/b2b/leave-the-organization)

[ゲスト アクセスと外部アクセスを使用して、組織外の人々とコラボレーションする](communicate-with-users-from-other-organizations.md)
