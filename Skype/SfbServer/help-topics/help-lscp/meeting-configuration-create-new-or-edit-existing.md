---
title: 会議の構成 新規の作成または既存の編集
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: 会議の構成の設定では、ユーザーによってスケジュールされている会議にユーザーが参加するときの操作方法を定義します。 これらの設定は、スケジュールされている会議にのみ適用されます。 クライアントで [今すぐ会議] オプションをクリックして作成されたアドホック会議には適用されません。
ms.openlocfilehash: 21cc12cd025edfc573e1e2f21ed08181f1a0c926
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099673"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>会議の構成: 新規作成または現在の形式のままで編集

会議の構成の設定では、ユーザーによってスケジュールされている会議にユーザーが参加するときの操作方法を定義します。 これらの設定は、スケジュールされている会議にのみ適用されます。 クライアントで [今すぐ会議] オプションをクリックして作成されたアドホック **会議には適用** されません。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのフィールドを示します。

- **スコープ** 作成または変更する会議構成のスコープ (グローバル、サイト、またはプール) を識別します。

- **名前** 会議の構成は既定で名前が付け、名前を変更することはできません。

- **PSTN 発信者がロビーをバイパスする** 公衆交換電話網 (PSTN) 電話回線を使用して会議にダイヤルインしているユーザーを自動的に許可するには、このチェック ボックスをオンにします。 その場合、発信者は、会議の発表者によって会議へのアクセスが許可されるまで、保留状態のまま電話会議ロビーで待機します。

- **発表者として指定する** 会議に参加するときに自動的に発表者として指定されるユーザーのカテゴリ (会議の開催者以外) を選択します。 この設定に関係なく、会議のスケジュール時に発表者を明示的に発表者として指定するか、会議中に発表者に明示的に昇格できます。 以下のオプションがあります:

  - **なし** 開催者以外のユーザーが発表者として自動的に指定しない場合は、このオプションを選択します。

  - **会社** 組織のメンバーのみを発表者として自動的に指定するには、このオプションを選択します。

  - **すべてのユーザー** 発表者になるユーザーを自動的に指定するには、このオプションを選択します。

- **既定で割り当てられた会議の種類** この設定は、Outlook Conferenceing Addin が常に開催者の割り当てられた会議を使用して会議をスケジュールするかどうかを制御します。つまり、スケジュールされた会議には常に同じ参加 URL と音声情報が含まれます。 このチェック ボックスをオンにすると、スケジュールされる会議には常に同じ参加 URL が与えられます。 このチェック ボックスをオフにすると、会議ごとに異なる参加 URL が使用されます。

- **既定で匿名ユーザーを許可する** 匿名 (つまり、認証されていない) ユーザーが既定で会議に出席できる場合は、このチェック ボックスをオンにします。 匿名ユーザーが既定で会議に出席できない場合は、このチェック ボックスをオフにします。

- **ロゴ URL** カスタム会議の招待に使用するイメージを含む URL を入力します。

- **ヘルプ URL** ユーザーが会議への参加を支援できる Web サイトの URL を入力します。

- **法的なテキスト URL** 会議の法的情報と免責事項を含む Web サイトの URL を入力します。

- **カスタム フッター テキスト** カスタム会議出席依頼で使用するテキストを入力します。

会議の構成の操作の詳細については、「操作」のドキュメントの「[Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings)」を参照してください。 大規模ミーティングの会議構成の設定については、「計画」のドキュメントの「[Setting Up Support for Large Meetings](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings)」を参照してください。