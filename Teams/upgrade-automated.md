---
title: 自動アップグレード |Skype Business から Teams へのアップグレード
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Skype for Business から Teams への自動アップグレードの概要
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ed959f74be1074ab8ed60b3fe54f06384b7990a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836169"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Skype for Business Online から Microsoft Teams への自動アップグレード

Microsoft は、小規模企業が2021年7月31日までに Skype for Business Online からの移行を成功させるために、チームの自動化されたアップグレードを提供しています。 自動アップグレードでは、ユーザーが必要とする技術タスクの数が減り、組織の準備、ユーザーの意識、チームのトレーニングに重点を置くことができます。

Skype for Business から Microsoft Teams へのアップグレードを成功させるには、技術とユーザーの準備を計画する必要があります。 始める準備ができたら、Skype for Business から Teams への正常な移行を実現するために、主要な推奨アクティビティと関連リソースを備えた[アップグレードアクションプラン](upgrade-basic.md)が提供されます。

## <a name="notifications-for-scheduled-customers"></a>スケジュールされているお客様への通知

Teams への自動アップグレードの対象となる Skype for Business Online のお客様は、スケジュールされたアップグレード日の30日前に、一連のアップグレード通知を受け取ります。 これらの通知は、管理メッセージセンターの投稿を*変更する計画*、グローバル管理者にメールをアップグレードする計画、およびアプリ内フラグをエンドユーザーにアップグレードする計画として提供されます。

これらの通知は、自動アップグレードのスケジュールされた日付を伝え、チームの導入と使用に役立つようにアップグレードのリソースおよびトレーニングにリンクします。また、自動アップグレードを延期するオプションをユーザーに提供します。スケジュールされた日付によってアップグレードする準備ができていないというイベント。

## <a name="the-automated-upgrade-experience"></a>自動アップグレード操作

自動アップグレードは、通知メール、メッセージセンター、および Teams 管理ポータルで伝達される、スケジュールされたアップグレード日に実行されます。 アップグレードには約15分かかります。これにより、エンドユーザーは引き続き Skype for Business Online の機能にアクセスできます。 アップグレードが完了して、ユーザーが Skype for Business Online をログアウトした場合、ユーザーは、メッセージング、会議、通話にチームを使用できます。

## <a name="the-post-upgrade-experience"></a>アップグレード後の操作

自動アップグレードが完了すると、[**共存] モード**は [Teams のみ] に設定され、Microsoft が別の共存モードに変更することのみができます。 管理者は、アップグレード前に[チーム専用モードの考慮事項](teams-only-mode-considerations.md)を確認する必要があります。 次の表は、Teams のみのユーザーエクスペリエンスの概要を示しています。


|  |  |
|---------|---------|
|**チャットと通話**     | <UL><LI>すべての通話とチャットは、Teams で開始および受信されます。<LI>ユーザーは、任意の Skype for Business ユーザーとの相互運用 (チャット/通話) を行うことができます<LI>ユーザーが Skype for Consumer を使用しているユーザーと通信できない<LI>ユーザーが Skype for Business にサインインしようとすると、Teams にリダイレクトされます。      </UL>  |
|**会議**     |  <UL><LI>ユーザーが Teams ですべての新しい会議をスケジュールする (プラグインは置き換えられる)    </UL>   |
|**移行されたデータ**     |<UL><LI>フェデレーションを含む、Skype for Business からの既存の連絡先 (ただし、配布リストはありません)<LI>既存の Skype for Business 会議 (オンプレミスとオンラインの両方) が Teams 会議に変換されます</UL>         |

## <a name="postponing-your-automated-upgrade"></a>自動アップグレードの延期

Skype for Business Online から Microsoft Teams への正常な移行には、チームの拡張された機能とパフォーマンスを活用できるように、組織での計画とユーザーの準備が必要です。 ただし、アップグレードを計画しているときに、現時点で組織が Teams にアップグレードする準備がまだ整っていない可能性があります。

チームへのスケジュールされた自動アップグレードに関する通知を受け取ったときに、後日延期したい場合は、Office 365 グローバル管理者が Teams 管理ポータルにログインして、[*延期*] ボタンをクリックします。 これにより、自動アップグレード日が30日後に表示されます。 延期後に Teams 管理ポータルを更新すると、新しい自動アップグレードの日付を含む通知が表示されます。

## <a name="requests-to-downgrade-to-skype-for-business"></a>Skype for Business へのダウングレード要求

Teams から SfBO への1回限りのダウングレードを許可し、テナントが Teams へのアップグレードを準備できるようにします。 ダウングレードされたテナントは、ダウングレード日から自動的にアップグレードされた60日間に再参加することになります。

## <a name="related-content"></a>関連コンテンツ

- [Microsoft Teams へのアップグレードを開始する](upgrade-start-here.md)
- [Skype for Business Online のサポート終了](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [Teams Only モードの考慮事項](teams-only-mode-considerations.md)

