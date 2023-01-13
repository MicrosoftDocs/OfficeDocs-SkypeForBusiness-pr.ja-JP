---
title: 機密性の高い Teams 会議にエンドツーエンドの暗号化を要求する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Teams 会議でエンドツーエンドの暗号化を有効にする方法について説明します。
ms.openlocfilehash: 091da268e8042707dd7e27094fde33d957a52d79
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800141"
---
# <a name="require-end-to-end-encryption-for-sensitive-teams-meetings"></a>機密性の高い Teams 会議にエンドツーエンドの暗号化を要求する

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

エンドツーエンドの暗号化は、中間ノードが暗号化を解除することなく、配信元の情報の暗号化と目的の宛先での暗号化解除です。 Teams の会議がエンド ツー エンドで暗号化されている場合、会議の参加者を除いて、誰も通信を聞いたり、表示したりすることはできません。 マイクロソフトを含む他の当事者は、復号化された会話にアクセスできません。

エンド ツー エンドの暗号化された会議は、2 つのパーティー間で行うことができます。パーティーが Windows または Mac 用の Teams デスクトップ クライアントの最新バージョンを使用している場合、iOS と Android 用の最新の更新プログラムを持つモバイル デバイス上にある場合、または最新の更新プログラムを使用して Windows デバイス上のTeams Rooms上にある場合。 ブラウザー経由で出席した会議のエンドツーエンドの暗号化はサポートされていません。

> [!Note]
> エンド ツー エンドの会議暗号化には、Teams Premiumが必要です。

エンドツーエンドの暗号化を有効にしない場合でも、Teams は業界標準に基づいて暗号化を使用して会議をセキュリティで保護します。 会議中に交換されるデータは、転送中と保存中に常にセキュリティで保護されます。 詳細については、「[Teams のメディアの暗号化](teams-security-guide.md#media-encryption)」を参照してください。

エンド ツー エンドの暗号化された会議中に、Teams は次の機能をセキュリティで保護します。

- オーディオ

- ビデオ

- 画面共有

[Microsoft 365 での暗号化](/microsoft-365/compliance/encryption) は、会議でのチャット、ファイル共有、プレゼンス、その他のコンテンツを保護します。 アプリ、アバター、リアクション、チャット、Q&A はエンドツーエンドで暗号化されません。

エンド ツー エンドの暗号化された会議では、次の機能を使用できません。

- ライブ キャプションと文字起こし

- 記録

- 一緒にモード、コンパニオン モード、大きなギャラリー

- ブレークアウト ルーム

組織がコンプライアンス記録を使用している場合、エンドツーエンドの暗号化は使用できません。 Teams がコンプライアンス レコーディングをサポートする方法の詳細については、「[通話と会議用の Teams ポリシーベースのレコーディングの概要](teams-recording-policy.md)」を参照してください。

## <a name="enable-end-to-end-encryption-for-meetings"></a>会議のエンドツーエンド暗号化を有効にする

既定では、会議のエンドツーエンド暗号化は有効になっていません。 これを有効にするには、Teams 管理者拡張暗号化ポリシーを使用します。

エンド ツー エンドの暗号化が有効になると、会議の開催者はエンド ツー エンドの暗号化を選択し、会議を作成できます。 会議テンプレートまたは秘密度ラベルを使用して、エンドツーエンドの暗号化を適用することもできます。

会議でエンドツーエンドの暗号化を有効にするには

1. Teams 管理センターで、[ **拡張暗号化ポリシー**] を選択します。

1. 更新するポリシーを選択します。

1. [ **エンド ツー エンドの会議の暗号化**] を **[無効] に設定しますが、ユーザーは上書きできます**。

1. **[保存]** を選択します。

## <a name="related-topics"></a>関連項目

[3 層の保護を使用して Teams 会議を構成する](configure-meetings-three-tiers-protection.md)

[1 対 1 の Microsoft Teams 通話にエンドツーエンドの暗号化を使用する](teams-end-to-end-encryption.md)
