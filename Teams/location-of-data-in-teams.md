---
title: Microsoft Teams のデータの場所
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: Microsoft Teams でデータが保存されている場所について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11d95858c39a2d555a4b1a7433b0a7dce0388293
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780266"
---
# <a name="location-of-data-in-microsoft-teams"></a>Microsoft Teams のデータの場所

Teams のデータは、Office 365 組織に関連付けられている地理的地域内に存在します。 現在、Teams でサポートされているのは、オーストラリア、カナダ、フランス、ドイツ、インド、日本、南アフリカ、韓国、スイス (リヒテンシュタインを含む)、英国連邦、英国、南北アメリカ、APAC、および EMEA 地域です。 

> [!IMPORTANT]
> Teams では現在、オーストラリア、カナダ、フランス、ドイツ、インド、日本、英国、英国、韓国、南アフリカ、スイス (リヒテンシュタインを含む) で、新しいテナントのみにデータ常駐品が提供されています。
> 新しいテナントは、Teams に 1 人のユーザーもサインインさせていない任意のテナントとして定義されます。 オーストラリア、インド、日本、韓国の既存のテナントは、引き続き APAC 地域に保存されています。 カナダの既存のテナントのデータは、南北アメリカに保存され続けます。 フランス、ドイツ、リヒテンシュタイン、アラブ首長国連邦、英国、南アフリカ、スイスの既存のテナントには、EMEA 地域にデータが保存されています。

## <a name="where-your-teams-data-is-stored"></a>チームデータが保存されている場所

テナントのデータが格納されている領域を確認するには、 [Microsoft 365 管理センター](https://portal.office.com/adminportal/home) > の**設定** > **組織プロファイル**に移動します。 下にスクロールして **[データの場所]** に移動します。

![管理センターの Teams を含むデータの場所テーブルのスクリーンショット](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a>残りのチームデータの場所

チームデータの保存場所は、コンテンツの種類によって異なります。 

![Teams コンテンツタイプと保存場所に保存されている場所を示す図](media/location-of-data-storage-at-rest.png)

詳細については、「 [Microsoft Teams アーキテクチャでの Ignite の分科セッション](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071)」を参照してください。

### <a name="core-teams-customer-data"></a>主要な Teams の顧客データ

お客様のテナントが、オーストラリア、カナダ、欧州連合、フランス、ドイツ、インド、日本、南アフリカ、韓国、スイス (リヒテンシュタインを含む)、英国連邦、英国、または米国内にある場合は、次のお客様のデータが保持されている場所に保存されます。

- チームチャット、チームとチャネルでの会話、画像、ボイスメールメッセージ、連絡先
- SharePoint Online サイトのコンテンツと、そのサイト内に保存されているファイル
- OneDrive for Business にアップロードされたファイル

#### <a name="chat-channel-messages-team-structure"></a>チャット、チャネルメッセージ、チーム構造

Teams のすべてのチームは、Office 365 グループとその SharePoint サイトと Exchange メールボックスによってサポートされます。 プライベートチャット (グループチャットを含む)、チャネルでの会話の一部として送信されるメッセージ、チームとチャネルの構造は、Azure で実行されているチャットサービスに格納されます。 また、データは、情報保護機能を有効にするために、ユーザーとグループのメールボックスの隠しフォルダーにも保存されています。

#### <a name="voicemail-and-contacts"></a>ボイスメールと連絡先

ボイスメールは Exchange に格納されます。 連絡先は Exchange ベースのクラウドデータストアに保存されます。 Exchange と Exchange ベースのクラウドストアでは、世界各地の datacenter geos のそれぞれにデータ常駐サービスが用意されています。 すべてのチームの場合、ボイスメールと連絡先は、オーストラリア、カナダ、フランス、ドイツ、インド、日本、英国、英国、南アフリカ、韓国、スイス (リヒテンシュタインを含む)、および米国に保存されています。 その他の国の場合、ファイルは、テナントのアフィニティに基づいて米国、ヨーロッパ、またはアジア太平洋地域に保存されます。

#### <a name="images-and-media"></a>画像とメディア

チャットで使用されるメディア (保存されていないが、元の Giphy サービス URL への参照リンクであるのに対して) は、チャットサービスと同じ場所に展開された Azure ベースメディアサービスに格納されます。

#### <a name="files"></a>ファイル

チャネルで他の人が共有しているファイル (OneNote や Wiki を含む) は、チームの SharePoint サイトに保存されます。 会議または通話中にプライベートチャットまたはチャットで共有されたファイルは、ファイルを共有しているユーザーのビジネスアカウント用の OneDrive にアップロードおよび保存されます。 Exchange、SharePoint、OneDrive では、世界各地の各 datacenter geos でデータ常駐サービスを既に提供しています。 したがって、既存のユーザーについては、すべてのファイル、OneNote ノートブック、チーム wiki コンテンツ、チームエクスペリエンスの一部であるメールボックスは、テナントのアフィニティに基づいて既に場所に保存されています。 ファイルは、オーストラリア、カナダ、フランス、ドイツ、インド、日本、英国、英国、南アフリカ、韓国、スイス (リヒテンシュタインを含む) の国内に保存されています。 その他の国の場合、ファイルは、テナントのアフィニティに基づいて米国、ヨーロッパ、またはアジア太平洋地域の場所に保存されます。

### <a name="datacenter-locations"></a>データセンターの場所

このセクションで説明する Teams サービスは、残りのデータを次の場所に保存します。

|国または地域  |データセンターの場所 |
|---------|---------|
|オーストラリア   |新しいサウスウェールズと Victoria         |
|カナダ    |ケベック市とトロント         |
|フランス    |Marseille とパリ         |
|ドイツ    |ベルリンと Frankfurt      |
|インド   |チェンナイ (と Pune        |
|日本    |東京 (Saitama) および大阪 ()         |
|リヒテンシュタイン   |ジュネーブと Zurich       |
|南アフリカ     |ヨハネルブルグとカーボベルデ         |
|韓国     |ソウルと Busan         |
|スイス    |ジュネーブと Zurich       |
|アラブ首長国連邦     |アブダビと Dubai         |
|英国     | Cardiff と London        |
|南北アメリカ–北、南 (AMER) |Bay、CA、Boydton、VA       |
|アジア太平洋 (APAC)  |シンガポール・香港        |
|ヨーロッパ、中東、アジア (EMEA)   |ダブリンとアムステルダム        |

> [!NOTE]
> リヒテンシュタインの場合、データはジュネーブと Zurich のスイスのデータセンターの残りの部分に保存されます。

### <a name="data-stored-with-a-third-party-storage-provider"></a>サードパーティストレージプロバイダーと共に保存されているデータ

ユーザーがサードパーティストレージプロバイダーを使用してファイルを保存することを許可している組織は、それらのサービスの保存場所に依存しているため、残りのサービスのデータの場所を個別に確認する必要があります。

- **タブ**: タブでは、ユーザーがアプリやサービスからチャネルに情報をピン留めすることができます。 そのため、データが保存されているタブの種類によって異なります。 タブ自体にデータが保存されることはありません。 たとえば、SharePoint のタブには、SharePoint サイトコレクションがプロビジョニングされた場所に基づいてデータが保存されます。 パートナーからの情報を含むタブは、パートナーによって使用されているシステムにデータを直接保存し、ビューを表示します。
- **その他のパートナーアプリ**: Microsoft は、Teams のエクスペリエンス内で使用されているパートナーからのアプリやサービスに対して、データ常駐サポートを提供していません。 これらのソリューションの情報を直接確認して、データの保存場所について確認します。

## <a name="see-also"></a>関連項目

- [Microsoft Teams でアラブ首長国のデータ常駐サービスを開始](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [Microsoft Teams で韓国のデータ常駐サービスが起動する](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [Microsoft Teams が南アフリカのデータ常駐サービスを発表](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [Microsoft Teams がフランスのデータ常駐サービスを起動する](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [Microsoft Teams がインドのデータ配信を開始します。その他の geos は近日中に公開されます。](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [Microsoft Teams がオーストラリアおよび日本のデータ常駐サービスを発表](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [Microsoft Teams では、近日中にカナダのデータ常駐、オーストラリア、日本が発売されます](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
