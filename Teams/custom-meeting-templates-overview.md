---
title: Microsoft Teams のカスタム会議テンプレートの概要
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ralphmaamari
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
appliesto:
- Microsoft Teams
description: Microsoft Teams Premium のカスタム会議テンプレートについて説明します。
ms.openlocfilehash: 0ed766141e09b9c26d8e8c6f5e8fdd12195ddb78
ms.sourcegitcommit: 4fdbd93aacb52a4fca68e31eb04d0495d4e27a10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/27/2022
ms.locfileid: "69672917"
---
# <a name="overview-of-custom-meeting-templates-in-microsoft-teams"></a>Microsoft Teams のカスタム会議テンプレートの概要

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Microsoft Teams Premium には、カスタム会議テンプレートを作成する機能が含まれています。 会議テンプレートを使用すると、会議の開催者が通常制御する会議設定を制御できます。 テンプレートを使用すると、組織内で一貫した会議エクスペリエンスを作成し、コンプライアンス要件とビジネス ルールを適用できます。

会議テンプレートは、設定を適用したり、既定値を設定したりするために使用できます。 各テンプレート設定は、会議の開催者が変更できないようにロックすることも、必要に応じて会議の開催者が変更できるようにロック解除したままにすることもできます。

会議テンプレートを使用して、次の会議設定を制御できます。

|Setting|説明|
|:------|:----------|
|チャット|会議チャットを使用できるかどうかを指定します。 会議の前後のチャットを防ぐためにも使用できます。|
|エンドツーエンドの暗号化|会議が暗号化されているかどうかを指定します。|
|ロビー|ロビーをバイパスして会議に直接参加できるユーザーを指定します。|
|出席者に表示される内容を管理する|会議の開催者が、他の会議参加者に表示される前に、画面で共有されているコンテンツをプレビューおよび承認できるかどうかを指定します。|
|出席者向けのマイクとカメラ|出席者がミュートを解除してカメラを使用できるかどうかを指定します。|
|呼び出し元が参加して退出したときに通知する|電話で通話しているユーザーが会議に参加または退出するときにサウンドが再生されるかどうかを指定します。|
|Q&A|出席者が Q&A 機能を使用して会議中に質問できるかどうかを指定します。|
|反応|出席者がリアクションを使用できるか、会議で手を挙げることができるか指定します。|
|記録|記録できるユーザーと、会議が自動的に記録されるかどうかを指定します。|
|秘密度ラベル|会議に使用する秘密度ラベルを指定します。|
|透かし|会議で画面上で共有されるカメラ フィードとコンテンツに透かしを使用するかどうかを指定します。|

テンプレートが役に立つ場合の例を次に示します。

- 特定の種類の会議に対して自動会議記録を強制する。
- チャットと出席者のカメラとオーディオを制限し、Q&プレゼンテーションスタイルの会議用の機能を使用する。
- ロビーをバイパスできるユーザーに対してより厳密な既定値を使用しますが、必要に応じて会議の開催者が設定を変更できるようにします。

会議テンプレートを作成する方法については、「[Microsoft Teams でカスタム会議テンプレートを作成](create-custom-meeting-template.md)する」を参照してください。

## <a name="templates-with-sensitivity-labels"></a>秘密度ラベルを持つテンプレート

テンプレートには、秘密度ラベルを指定するオプションがあります。 ラベルは、テンプレートに関係なく、会議に直接適用することもできます。 秘密度ラベルは、テンプレートと同じ設定の一部を制御できます。

- エンドツーエンドの暗号化
- 会議チャット
- 自動的にレコードを記録する
- ロビーをバイパスできるユーザー
- 発表できるユーザー
- 記録できるユーザー
- 透かし

これらの設定のいずれかがラベルで構成されている場合は、テンプレート内のこれらの設定をオーバーライドします。

## <a name="templates-included-with-teams"></a>Teams に含まれるテンプレート

Teams Premium には、ユーザーが利用できる既定の会議テンプレートがいくつか含まれています。

- 大規模な会議
- 保護された会議
- タウン ホール
- [仮想予定](virtual-appointment-meeting-template.md)
- ウェビナー

さらに、これらのテンプレートはMicrosoft Teams for Educationで使用できます。

- クラス
- ディスカッション グループ
- 講義
- 親教師会議

必要に応じて、これらのテンプレートの設定を更新できます。

## <a name="related-topics"></a>関連項目

[3 層の保護を使用して Teams 会議を構成する](configure-meetings-three-tiers-protection.md)

[Teams 会議テンプレート、秘密度ラベル、管理ポリシーを一緒に使用する](meeting-templates-sensitivity-labels-policies.md)
