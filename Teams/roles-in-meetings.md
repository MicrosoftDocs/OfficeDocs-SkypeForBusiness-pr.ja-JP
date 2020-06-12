---
title: Teams 会議でのプレゼンターと参加者の機能
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams 会議でのプレゼンターと参加者の機能について説明します。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: c8433d4caa0defbe83114ac4027c10b6bf61a725
ms.sourcegitcommit: 862ba1d2b3bd4622b1b0baa15096c29c591cc6c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2020
ms.locfileid: "44702692"
---
<a name="presenter-and-participant-capabilities-in-a-teams-meeting"></a>Teams 会議でのプレゼンターと参加者の機能
======================================================

Microsoft Teams 会議は、多くの種類の参加者をサポートしています。 参加者は、組織内外の役割に基づいて、さまざまな会議の機能にアクセスできます。

使用可能な会議の機能は次のとおりです。

- チャット (写真とステッカーを含む)
- 会議のメモ
- ホワイトボード
- 記録
- ファイル
- 会議の予約 (会議のみ)

この記事では、これらの参加者の機能と、会議の機能へのアクセス許可について説明します。

## <a name="presenters-and-organizers"></a>プレゼンターと主催者

プレゼンターと主催者は次のとおりです。

- 自分の所属組織のプレゼンター
- 他の組織のプレゼンター - 匿名および外部の参加者が含まれます。 プレゼンターは主催者によって指定され、主催者からの個人的な招待が必要です。

プレゼンターと主催者は、会議またはライブ イベントのすべての機能にアクセスできます。

## <a name="participants"></a>参加者

会議参加者はいくつかの種類があります。

- [テナント内の参加者](#in-tenant-participant)
- [ゲスト参加者](#guest-participant)
- [外部 (フェデレーション) 参加者](#external-federated-participant)
- [匿名参加者](#anonymous-participant)

### <a name="in-tenant-participant"></a>テナント内の参加者

テナント内の参加者は組織に属しており、テナントの資格情報を持っています。 この参加者の詳細については、「[セキュリティと Microsoft Teams](teams-security-guide.md#participant-types)」をご覧ください。

|会議  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **機能**        | 事前会議 | 会議中 | 会議後 |
| チャット | はい | はい | はい |
| 会議のメモ | はい | はい |はい |
| ホワイトボード | はい | はい |はい |
| 記録 | 該当なし |はい | はい |
| ファイル | はい | はい | はい |
| 会議の予約 | はい | 該当なし | 該当なし |
|||||||

### <a name="guest-participant"></a>ゲスト参加者

ゲスト参加者とは、Azure Active Directory B2B プラットフォームに基づいて、組織のテナント内の Teams またはその他のリソースにアクセスするように招待された別の組織からの参加者です。 ゲスト ユーザーは、定例会議やチャネル会議に参加するよう招待できます。 ゲスト参加者の詳細については、「[ゲストのエクスペリエンスについて](guest-experience.md#comparison-of-team-member-and-guest-capabilities)」をご覧ください。

| 会議 |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **機能**        | 事前会議 | 会議中 | 会議後 |
| チャット | はい | はい | はい |
| 会議のメモ | はい | はい | はい |
| ホワイトボード | いいえ | いいえ |いいえ |
| 記録 | 該当なし |いいえ | いいえ |
| ファイル | はい | はい | はい |
| 会議の予約 | いいえ | 該当なし | 該当なし |
|||||||

### <a name="external-federated-participant"></a>外部 (フェデレーション) 参加者

外部参加者とは、別の組織の Teams を使用して、会議への参加を招待されているが、それ以外の場合は組織の他の共有リソースにアクセスできないユーザーです。 外部ユーザーの参加者は、自分の組織と同じ ID 名で会議名簿に表示されます。 外部参加者の詳細については、「[別の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md#external-access)」をご覧ください。

| 会議 ||
|-|-|-|
| **機能** |||
| チャット | はい |
| 会議のメモ | 該当なし |  
| ホワイトボード | 該当なし |
| 記録 | 該当なし |  
| ファイル | 該当なし |
| 会議の予約 | 該当なし |
|||

### <a name="anonymous-participant"></a>匿名参加者

匿名参加者は外部ユーザーのようですが、自分の ID は会議に表示されません。 参加時に、手動でニックネームを入力します。 匿名参加者の詳細については、「[セキュリティと Microsoft Teams](teams-security-guide.md#participant-types)」をご覧ください。

| 会議  | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **機能**        | 事前会議 | 会議中 | 会議後 |
| チャット | 該当なし | はい | 該当なし |
| 会議のメモ | 該当なし | X | 該当なし |
| ホワイトボード | 該当なし | X | 該当なし |
| 記録 | 該当なし | X | 該当なし |
| ファイル | 該当なし | X | 該当なし |
| 会議の予約 | 該当なし | 該当なし | 該当なし |
|||||||

## <a name="related-topics"></a>関連項目

[セキュリティと Microsoft Teams](teams-security-guide.md)

[Teams でのゲスト アクセス](guest-access.md)
