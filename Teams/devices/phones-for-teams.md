---
title: Microsoft Teams 用の電話機
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: kponnus
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: この記事では、Microsoft Teams 用に認定されている電話機と、それらの電話機でサポートされている機能のリストを取り上げています。
ms.openlocfilehash: a4fc3a6516881d6f865b22cbf92d85af6859cb14
ms.sourcegitcommit: e07b2d7470b93e52b9e85207db0d6fa3a136efd9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48787031"
---
# <a name="phones-for-microsoft-teams"></a>Microsoft Teams 用の電話機

Microsoft Teams では、従来の電話機エクスペリエンスを必要とするユーザー向けに卓上電話機製品をサポートしています。 この記事では、Teams 電話の包括的な概要を説明し、Microsoft 電話システムソリューションの一部として Microsoft Teams 電話の計画、配布、管理を行う方法について説明します。 

高品質で信頼できる Microsoft Teams を携帯電話で実現するために、お客様は、Lenovo、Polycom、および Audiocodes を使用して、さまざまな卓上電話と会議室のオーディオデバイスを開発し、認定しています。 Teams デバイスに関する最新情報と最新情報を取得するには、「 [Teams Marketplace](https://office.com/teamsdevices)」を参照してください。

電話を管理するには、グローバル管理者、Teams サービス管理者、または Teams デバイス管理者である必要があります。管理者ロールの詳細については、「 [Microsoft teams 管理者ロールを使用してチームを管理する](../using-admin-roles.md)」を参照してください。

## <a name="features-supported-by-teams-phones"></a>Teams 電話でサポートされている機能

チームで認定された電話には、ユーザーがジョブを実行し、使用を管理するためのさまざまな機能が用意されています。 ここでは、Teams で認定された電話で利用できる機能の概要を説明します。

- **認証** 電話は先進認証を使用して、サインインとセキュリティを強化します。 ユーザーは、電話にユーザー名とパスワードを入力するか、PC/smartphone などの別のデバイスからサインインしてサインインできます。
- **スピードダイヤルと通話履歴** ユーザーは、連絡先、通話履歴、ボイスメールにすばやくアクセスできます。 相手は連絡先を簡単に管理し、電話から直接通話を発信できます。
- **会議と通話** ユーザーは、チームのワンタッチ結合を使って、スケジュールを表示して、簡単に会議に参加することができます。
- **通話グループ** 通話グループに参加している電話の担当者は、通話の可用性を簡単に管理し、通話キューからの着信を承諾または拒否することができます。
- **ユーザーの委任** エグゼクティブアシスタントと管理者は、経営陣による通話の傍受を管理することができます。エグゼクティブの代理として通話を発信してください。エグゼクティブが保留にした通話を引き継ぐことができます。エグゼクティブが通話中であるか、保留中であるかを監視します。
- **ホット desking** ユーザーは、電話にサインインするだけで、連絡先、会議、その他の環境設定を取得できます。 完了したら、サインアウトして、次のユーザーのために電話を残しておくことができます。
- **ビデオ** ビデオをサポートしている電話では、ユーザーは自分のコンピューターの場合と同様に、通話やビデオ会議に参加できます。 ユーザーは、携帯電話のカメラシャッターとマイクミュートスイッチを使用して、プライバシーを維持することができます。
- **共同** 作業の向上64ビット版の Teams デスクトップクライアントを実行している Windows PC に接続している場合、固定された方法で電話をロックおよびロック解除することができます。
- **アクセシビリティ** 電話には、他のユーザーが簡単に使用できるように、ハイコントラストテキストなどのいくつかのアクセシビリティ機能があります。
- **動的で強化された E911 のサポート** 911を呼び出すサインインしたユーザーは、電話でその場所を確認できます。 
    > [!IMPORTANT]
    > 電話にサインインしていない場合や、インターネットに接続されていない場合は、911通話を発信することはできません。 この問題が発生すると、電話に通知が表示されます。

上記の機能に加えて、電話にサインインしているユーザーに割り当てられているライセンスと電話ポリシーの種類に応じて、使用できる機能を制御することができます。 たとえば、個人アカウントで電話にサインインしたユーザーは、通話、会議、ボイスメールなどのさまざまな機能にアクセスできます。 電話にサインインする一般的な市外局番のライセンスが割り当てられているアカウントは、限られた範囲の機能にしかアクセスできません。通話履歴と会議のスケジュールは保持されないことがあります。たとえば、ユーザーのプライバシーを保護することができます。

## <a name="required-licenses"></a>必要なライセンス

Teams ライセンスは、 [Microsoft 365 および Office 365 サブスクリプション](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)の一部として購入できます。 電話で Teams を使用するために必要なライセンスの詳細については、「利用可能な [電話システムライセンス](https://products.office.com/microsoft-teams/voice-calling)」を参照してください。

Teams の入手方法については[Microsoft Teams へのアクセス権を取得するにはどうしたらよいですか?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)を参照してください。

## <a name="deploy-your-phones-using-intune"></a>Intune を使用して電話を展開する

Intune を使用してチームの表示を展開する方法について詳しくは、「 [チームの電話とチームの表示を展開](phones-displays-deploy.md)する」をご覧ください。

## <a name="manage-your-phones"></a>電話を管理する

Microsoft Teams 管理センターを使用して、チームの電話を管理し、最新の状態に維持します。 詳細については、「 [Teams でデバイスを管理する](device-management.md)」を参照してください。

## <a name="upgrade-your-phones-to-teams-displays"></a>電話を Teams ディスプレイにアップグレードする

[Microsoft Teams の表示](teams-displays.md) は、さまざまな機能を備えたオールインワンの専用チームデバイスであり、これを利用することで、環境のタッチスクリーンとハンズフリーのエクスペリエンスが Cortana によって実現されます。 Teams を表示することで、ユーザーはマイク、カメラ、スピーカー (または Bluetooth ヘッドセット) を使用して、信頼性の高い通話と会議のエクスペリエンスを実現できます。 Teams では、ユーザーの Windows Pc と統合して、シームレスなクロスデバイス操作を可能にするコンパニオンエクスペリエンスを実現します。

組織内のチームの電話を、Microsoft Teams 管理センターの Teams の表示にアップグレードできます。 このオプションは、Teams ディスプレイへのアップグレードをサポートしている電話に対してのみ使用できます。 詳細については、「チーム [の電話を teams のディスプレイにアップグレードする](upgrade-phones-to-displays.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Teams Marketplace](https://office.com/teamsdevices)

[Microsoft Teams 認定 IP 電話](teams-ip-phones.md)

