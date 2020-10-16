---
title: Microsoft Teams のデータの場所
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: この記事では、Microsoft Teams におけるデータの地理的な場所について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c16065a864ac82cdf5f11c0d2c8254b648731cac
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121687"
---
# <a name="location-of-data-in-microsoft-teams"></a>Microsoft Teams のデータの場所

Teams のデータはご利用の Microsoft 365 または Office 365 の組織に関連付けられている地理的領域内に存在します。 現在、Teams は、オーストラリア、カナダ、フランス、ドイツ、インド、日本、南アフリカ、韓国、スイス (リヒテンシュタインを含む)、アラブ首長国連邦、英国、南北アメリカ、APAC、および EMEA 地域をサポートしています。 

> [!IMPORTANT]
> Teams は現在、新しいテナントに対して、オーストラリア、カナダ、フランス、ドイツ、インド、日本、アラブ首長国連邦、英国、韓国、南アフリカ、スイス (リヒテンシュタインを含む) にデータ所在地を提供しています。
> 新しいテナントは、Teams に 1 人のユーザーもサインインさせていない任意のテナントとして定義されます。 オーストラリア、インド、日本、韓国の既存のテナントは、引き続き APAC 地域に保存されている Teams のデータを保有します。 カナダの既存のテナントのデータは、引き続き南北アメリカに保存されます。 フランス、ドイツ、リヒテンシュタイン、アラブ首長国連邦、英国、南アフリカ、スイスの既存のテナントは、そのデータが EMEA 地域に保存されます。

## <a name="where-your-teams-data-is-stored"></a>Teams データの保存場所

ご利用のテナントのデータがどの地域に格納されるかを確認するには、[[Microsoft 365 管理センター]](https://portal.office.com/adminportal/home) > **[設定]** > **[組織プロファイル]** に移動してください。 下にスクロールして **[データの場所]** に移動します。

![管理センターの、Teams を含む、データの場所の表を示すスクリーンショット](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a>Teams 保存データの場所

Teams データは、コンテンツの種類に応じて異なる方法で保存されます。 

![Teams のコンテンツの種類とそれらが保存されている場所を示す図](media/location-of-data-storage-at-rest.png)

詳細なディスカッションについては、「[Microsoft Teams アーキテクチャに関する Ignite ブレイクアウト セッション](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071)」を確認してください。

### <a name="core-teams-customer-data"></a>Teams の主要な顧客データ

テナントが、オーストラリア、カナダ、欧州連合、フランス、ドイツ、インド、日本、南アフリカ、韓国、スイス (リヒテンシュタインを含む)、アラブ首長国連邦、英国、または米国でプロビジョニングされている場合、Microsoft はその場所にのみ次の顧客データを保存します:

- Teams のチャット、チームとチャネルの会話、画像、ボイスメール メッセージ、および連絡先
- SharePoint Online サイトのコンテンツと、そのサイト内に格納されているファイル
- OneDrive for Business にアップロードしたファイル

#### <a name="chat-channel-messages-team-structure"></a>チャット、チャネル メッセージ、チーム構造

Teams のすべてのチームは、Microsoft 365 グループとその SharePoint サイトおよび Exchange メールボックスによって支えられています。 プライベート チャット （グループ チャットを含む）、チャネルでの会話の一部として送信されるメッセージ、およびチームとチャネルの構造は、Azureで実行されているチャット サービスに格納されます。 データは、情報保護機能を有効にするために、ユーザーおよびグループのメールボックスの隠しフォルダーにも格納されます。

#### <a name="voicemail-and-contacts"></a>ボイスメールと連絡先

ボイスメールは Exchange に格納されます。 連絡先は Exchange ベースのクラウド データ ストアに格納されます。 Exchange と Exchange ベースのクラウド ストアは、世界中の各データ センター地域ですでにデータ所在地を提供しています。 すべてのチームについて、ボイスメールと連絡先は、オーストラリア、カナダ、フランス、ドイツ、インド、日本、アラブ首長国連邦、英国、南アフリカ、韓国、スイス (リヒテンシュタインを含む)、米国の国内に保存されています。 他のすべての国では、ファイルはテナントのアフィニティに基づいて米国、ヨーロッパ、またはアジア太平洋地域に保存されます。

#### <a name="images-and-media"></a>画像とメディア

チャットで使用されるメディア （保存されていないが、元の Giphy サービス URL への参照リンクである Giphy GIF を除き、Giphy は Microsoft 以外のサービスです） は、チャット サービスと同じ場所に展開される Azure ベースのメディア サービスに格納されます。

#### <a name="files"></a>ファイル

チャネルで共有されているファイル （OneNote と Wiki を含む） は、チームの SharePoint サイトに保存されます。 プライベート チャット、または会議中または通話中のチャットで共有されたファイルは、ファイルを共有するユーザーのビジネス アカウントの OneDrive にアップロードおよび保存されます。 Exchange、SharePoint、および OneDrive は、世界中の各データセンター地域ですでにデータの所在地を提供しています。 そのため、既存のお客様については、Teams エクスペリエンスの一部であるすべてのファイル、OneNote ノートブック、Teams wiki コンテンツ、メールボックスは、テナントのアフィニティに基づいた場所に既に保存されています。 ファイルは、オーストラリア、カナダ、フランス、ドイツ、インド、日本、アラブ首長国連邦、英国、南アフリカ、韓国、スイス (リヒテンシュタインを含む) の国内に保存されています。 他のすべての国では、ファイルはテナントのアフィニティに基づいて米国、ヨーロッパ、またはアジア太平洋地域に保存されます。

### <a name="datacenter-locations"></a>データセンターの場所

このセクションで説明する Teams サービスは、保存データを次の場所に保存します:

|国または地域  |データセンターの場所 |
|---------|---------|
|オーストラリア   |ニューサウスウェールズ州とビクトリア州         |
|カナダ    |ケベックシティとトロント         |
|フランス    |マルセイユとパリ         |
|ドイツ    |ベルリンとフランクフルト      |
|インド   |チェンナイとプネー        |
|日本    |東京 （埼玉） と大阪         |
|リヒテンシュタイン   |ジュネーブとチューリッヒ       |
|南アフリカ     |ヨハネスブルグとケープタウン         |
|韓国     |ソウルと釜山         |
|スイス    |ジュネーブとチューリッヒ       |
|アラブ首長国連邦     |アブダビとドバイ         |
|英国     | カーディフとロンドン        |
|南北アメリカ – 北および南 （アメリカ） |カリフォルニア州ベイとバージニア州ボイドトン       |
|アジア太平洋 （APAC）  |シンガポールと香港        |
|ヨーロッパ、中東、およびアジア （EMEA）   |ダブリンとアムステルダム        |

> [!NOTE]
> リヒテンシュタインの場合、保存データはジュネーブとチューリッヒのスイスのデータ センターに格納されます。

### <a name="data-stored-with-a-third-party-storage-provider"></a>サードパーティのストレージ プロバイダーに保存されているデータ

ユーザーがサードパーティのストレージ プロバイダーを使用してファイルを保存することを許可している組織は、それらのサービスのストレージの場所に依存しているため、それらのサービスの保存データの場所を個別に確認する必要があります。

- **タブ**: タブを使用すると、ユーザーがアプリとサービスの情報をチャネルにピン留めすることができます。 したがって、データが保存されているタブの種類によって異なります。 タブ自体はデータを保存しません。 たとえば、[SharePoint] タブには、SharePoint サイト コレクションがプロビジョニングされた場所に基づいてデータが格納されます。 パートナーからの情報を含むタブは、パートナーが使用するシステムにデータを直接保存し、ビューのみを表示します。
- **その他のパートナー アプリ**: Microsoft は、Teams エクスペリエンス内で使用している可能性のあるパートナーからのアプリとサービスに対して、データの所在地のサポートを提供していません。 データが保存されている場所については、これらのソリューションの情報を直接確認してください。

## <a name="see-also"></a>関連項目

- [Microsoft Teams はアラブ首長国連邦データ所在地を立ち上げます](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [Microsoft Teams は韓国データ所在地を立ち上げます](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [Microsoft Teams は南アフリカデータ所在地を立ち上げます](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [Microsoft Teams はフランスデータ所在地を立ち上げます](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [Microsoft Teams はインドデータ所在地を立ち上げ、その他の地域は近日公開です](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [Microsoft Teams はオーストラリアおよび日本のデータ所在地を立ち上げます](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [Microsoft Teams はカナダデータ所在地を立ち上げ、オーストラリアと日本は近日公開です](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
