<img width="784" height="1600" alt="image" src="https://github.com/user-attachments/assets/ca18fbf3-ffcb-4a24-bdb0-6848f0afefc4" />
<img width="786" height="1600" alt="image" src="https://github.com/user-attachments/assets/6601c9f8-ac96-449e-bd23-3ef8d75fdcae" />
<img width="802" height="1600" alt="image" src="https://github.com/user-attachments/assets/6a3c7d17-2124-40a9-b95a-538dabab2057" />
<img width="779" height="1599" alt="image" src="https://github.com/user-attachments/assets/3507a243-311b-4a24-aeb1-5d757001e4de" />




import React, { useState } from 'react';
import { ChefHat, Search, Heart, Clock, Users, Flame, Book, Home, Bookmark, User } from 'lucide-react';

const RecipeApp = () => {
  const [activeTab, setActiveTab] = useState('home');
  const [favorites, setFavorites] = useState(new Set());
  const [selectedRecipe, setSelectedRecipe] = useState(null);
  const [searchQuery, setSearchQuery] = useState('');

  const recipes = [
    {
      id: 1,
      name: 'Nasi Goreng Spesial',
      category: 'Makanan Utama',
      image: 'https://images.unsplash.com/photo-1512058564366-18510be2db19?w=400',
      time: '25 menit',
      servings: 4,
      difficulty: 'Mudah',
      calories: 450,
      ingredients: [
        '3 piring nasi putih',
        '2 butir telur',
        '100gr ayam fillet, potong dadu',
        '3 siung bawang putih, cincang',
        '5 siung bawang merah, iris',
        '2 sdm kecap manis',
        '1 sdt terasi',
        'Garam, merica secukupnya',
        'Minyak untuk menumis',
        'Daun bawang untuk garnish'
      ],
      steps: [
        'Panaskan minyak, tumis bawang putih dan bawang merah hingga harum',
        'Masukkan ayam, masak hingga berubah warna',
        'Masukkan telur, orak-arik hingga setengah matang',
        'Tambahkan nasi, aduk rata',
        'Beri kecap manis, terasi, garam, dan merica. Aduk hingga bumbu meresap',
        'Masak dengan api besar sambil terus diaduk selama 3-5 menit',
        'Tambahkan daun bawang, aduk sebentar',
        'Angkat dan sajikan hangat'
      ]
    },
    {
      id: 2,
      name: 'Soto Ayam Kuning',
      category: 'Sup',
      image: 'https://images.unsplash.com/photo-1604908177453-7462950a6a3f?w=400',
      time: '45 menit',
      servings: 6,
      difficulty: 'Sedang',
      calories: 320,
      ingredients: [
        '500gr ayam, potong',
        '2 liter air',
        '3 batang serai, memarkan',
        '4 lembar daun jeruk',
        '2 cm lengkuas, memarkan',
        '5 siung bawang putih',
        '8 butir bawang merah',
        '2 cm kunyit',
        '1 sdt ketumbar',
        'Garam dan gula secukupnya',
        'Pelengkap: tauge, kubis, telur rebus, kerupuk'
      ],
      steps: [
        'Rebus ayam dengan air hingga empuk, sisihkan kaldu',
        'Haluskan bawang putih, bawang merah, kunyit, dan ketumbar',
        'Tumis bumbu halus hingga harum',
        'Masukkan bumbu tumis ke dalam kaldu ayam',
        'Tambahkan serai, daun jeruk, dan lengkuas',
        'Masak hingga mendidih dan bumbu meresap',
        'Beri garam dan gula, koreksi rasa',
        'Sajikan dengan pelengkap'
      ]
    },
    {
      id: 3,
      name: 'Rendang Daging Sapi',
      category: 'Makanan Utama',
      image: 'https://images.unsplash.com/photo-1585937421612-70e008a2c75e?w=400',
      time: '3 jam',
      servings: 8,
      difficulty: 'Sulit',
      calories: 580,
      ingredients: [
        '1 kg daging sapi, potong kotak',
        '1 liter santan kental',
        '500ml santan encer',
        '10 butir bawang merah',
        '6 siung bawang putih',
        '10 cabai merah besar',
        '5 cm jahe',
        '4 cm lengkuas',
        '3 batang serai',
        '5 lembar daun jeruk',
        '3 lembar daun kunyit',
        'Asam kandis',
        'Garam dan gula merah'
      ],
      steps: [
        'Haluskan bawang merah, bawang putih, cabai, jahe',
        'Tumis bumbu halus dengan lengkuas, serai, daun jeruk, dan daun kunyit hingga harum',
        'Masukkan daging, aduk hingga berubah warna',
        'Tuang santan encer, masak hingga meresap',
        'Tambahkan santan kental, asam kandis, garam, dan gula merah',
        'Masak dengan api kecil sambil terus diaduk',
        'Masak hingga santan menyusut dan berminyak (sekitar 3 jam)',
        'Rendang siap disajikan'
      ]
    },
    {
      id: 4,
      name: 'Gado-Gado Jakarta',
      category: 'Sayuran',
      image: 'https://images.unsplash.com/photo-1546069901-ba9599a7e63c?w=400',
      time: '30 menit',
      servings: 4,
      difficulty: 'Mudah',
      calories: 280,
      ingredients: [
        'Kangkung, rebus',
        'Kol, potong dan rebus',
        'Tauge, seduh air panas',
        'Kentang, rebus dan potong',
        'Tempe goreng',
        'Tahu goreng',
        'Telur rebus',
        'Timun, iris',
        'Bumbu kacang: 200gr kacang tanah goreng, 3 cabai merah, 2 siung bawang putih, gula merah, air asam jawa, garam'
      ],
      steps: [
        'Haluskan kacang tanah, cabai, dan bawang putih',
        'Masak bumbu kacang dengan air, tambahkan gula merah dan air asam jawa',
        'Aduk hingga mengental, koreksi rasa',
        'Tata sayuran rebus, tempe, tahu, telur, dan timun di piring',
        'Siram dengan bumbu kacang',
        'Tambahkan kerupuk sebagai pelengkap',
        'Sajikan segera'
      ]
    },
    {
      id: 5,
      name: 'Es Cendol Dawet',
      category: 'Minuman',
      image: 'https://images.unsplash.com/photo-1563805042-7684c019e1cb?w=400',
      time: '40 menit',
      servings: 6,
      difficulty: 'Mudah',
      calories: 220,
      ingredients: [
        '100gr tepung hunkwe',
        '50gr tepung beras',
        '600ml air daun pandan',
        'Pewarna hijau alami (daun suji)',
        'Kuah: 200gr gula merah, 100ml air, 2 lembar daun pandan',
        '400ml santan kental',
        'Es batu'
      ],
      steps: [
        'Campur tepung hunkwe dan tepung beras dengan air daun pandan',
        'Masak sambil diaduk hingga mengental',
        'Cetak cendol dengan cetakan ke dalam air es',
        'Rebus gula merah dengan air dan daun pandan hingga larut',
        'Saring dan dinginkan',
        'Masak santan dengan sedikit garam, dinginkan',
        'Sajikan cendol dengan kuah gula merah, santan, dan es batu'
      ]
    },
    {
      id: 6,
      name: 'Martabak Manis',
      category: 'Cemilan',
      image: 'https://images.unsplash.com/photo-1554520735-0a6b8b6ce8b7?w=400',
      time: '60 menit',
      servings: 4,
      difficulty: 'Sedang',
      calories: 420,
      ingredients: [
        'Adonan: 250gr tepung terigu, 2 butir telur, 50gr gula pasir, 1 sdt ragi instan, 300ml susu cair, 1/2 sdt garam, 50ml minyak sayur',
        'Topping: coklat meses, keju parut, kacang tanah sangrai, mentega'
      ],
      steps: [
        'Campur tepung, gula, dan ragi',
        'Tambahkan telur dan susu, aduk rata',
        'Diamkan adonan 45 menit hingga mengembang',
        'Panaskan wajan anti lengket',
        'Tuang adonan, tutup hingga matang dan berlubang',
        'Olesi mentega, beri topping sesuai selera',
        'Lipat dan potong-potong',
        'Sajikan hangat'
      ]
    }
  ];

  const categories = ['Semua', 'Makanan Utama', 'Sup', 'Sayuran', 'Minuman', 'Cemilan'];

  const filteredRecipes = recipes.filter(recipe => 
    (searchQuery === '' || recipe.name.toLowerCase().includes(searchQuery.toLowerCase()) || 
    recipe.category.toLowerCase().includes(searchQuery.toLowerCase())) &&
    (activeTab === 'home' || (activeTab === 'favorites' && favorites.has(recipe.id)))
  );

  const toggleFavorite = (id) => {
    const newFavorites = new Set(favorites);
    if (newFavorites.has(id)) {
      newFavorites.delete(id);
    } else {
      newFavorites.add(id);
    }
    setFavorites(newFavorites);
  };

  const RecipeCard = ({ recipe }) => (
    <div 
      onClick={() => setSelectedRecipe(recipe)}
      className="bg-white rounded-2xl overflow-hidden shadow-lg hover:shadow-2xl transition-all duration-300 cursor-pointer group"
      style={{
        border: '1px solid #f0f0f0'
      }}
    >
      <div className="relative overflow-hidden" style={{ height: '200px' }}>
        <img 
          src={recipe.image} 
          alt={recipe.name}
          className="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500"
        />
        <div className="absolute top-3 right-3 bg-white rounded-full p-2 shadow-lg">
          <Heart
            onClick={(e) => {
              e.stopPropagation();
              toggleFavorite(recipe.id);
            }}
            className={`w-5 h-5 cursor-pointer transition-all ${
              favorites.has(recipe.id) ? 'fill-red-500 text-red-500' : 'text-gray-400'
            }`}
          />
        </div>
        <div className="absolute bottom-0 left-0 right-0 bg-gradient-to-t from-black/70 to-transparent p-4">
          <span className="text-xs text-white bg-orange-500 px-3 py-1 rounded-full font-medium">
            {recipe.category}
          </span>
        </div>
      </div>
      <div className="p-4">
        <h3 className="font-bold text-lg mb-2 text-gray-800">{recipe.name}</h3>
        <div className="flex items-center gap-4 text-sm text-gray-600">
          <div className="flex items-center gap-1">
            <Clock className="w-4 h-4 text-orange-500" />
            <span>{recipe.time}</span>
          </div>
          <div className="flex items-center gap-1">
            <Users className="w-4 h-4 text-orange-500" />
            <span>{recipe.servings} porsi</span>
          </div>
          <div className="flex items-center gap-1">
            <Flame className="w-4 h-4 text-orange-500" />
            <span>{recipe.calories} kal</span>
          </div>
        </div>
      </div>
    </div>
  );

  const RecipeDetail = ({ recipe }) => (
    <div className="fixed inset-0 bg-black/60 flex items-center justify-center p-4 z-50 overflow-y-auto"
         onClick={() => setSelectedRecipe(null)}>
      <div className="bg-white rounded-3xl max-w-2xl w-full max-h-[90vh] overflow-y-auto"
           onClick={(e) => e.stopPropagation()}
           style={{
             animation: 'slideUp 0.3s ease-out'
           }}>
        <div className="relative" style={{ height: '300px' }}>
          <img 
            src={recipe.image} 
            alt={recipe.name}
            className="w-full h-full object-cover"
          />
          <button 
            onClick={() => setSelectedRecipe(null)}
            className="absolute top-4 right-4 bg-white rounded-full w-10 h-10 flex items-center justify-center shadow-lg hover:bg-gray-100 transition-colors"
          >
            <span className="text-2xl leading-none">×</span>
          </button>
          <div className="absolute top-4 left-4">
            <Heart
              onClick={(e) => {
                e.stopPropagation();
                toggleFavorite(recipe.id);
              }}
              className={`w-8 h-8 cursor-pointer transition-all ${
                favorites.has(recipe.id) ? 'fill-red-500 text-red-500' : 'text-white fill-white'
              }`}
            />
          </div>
        </div>
        
        <div className="p-6">
          <div className="mb-4">
            <span className="text-sm text-white bg-orange-500 px-4 py-1.5 rounded-full font-medium">
              {recipe.category}
            </span>
          </div>
          
          <h2 className="text-3xl font-bold mb-4 text-gray-800">{recipe.name}</h2>
          
          <div className="grid grid-cols-3 gap-4 mb-6 p-4 bg-orange-50 rounded-2xl">
            <div className="text-center">
              <Clock className="w-6 h-6 text-orange-500 mx-auto mb-1" />
              <div className="text-sm text-gray-600">Waktu</div>
              <div className="font-bold text-gray-800">{recipe.time}</div>
            </div>
            <div className="text-center">
              <Users className="w-6 h-6 text-orange-500 mx-auto mb-1" />
              <div className="text-sm text-gray-600">Porsi</div>
              <div className="font-bold text-gray-800">{recipe.servings}</div>
            </div>
            <div className="text-center">
              <Flame className="w-6 h-6 text-orange-500 mx-auto mb-1" />
              <div className="text-sm text-gray-600">Kalori</div>
              <div className="font-bold text-gray-800">{recipe.calories}</div>
            </div>
          </div>

          <div className="mb-6">
            <h3 className="text-xl font-bold mb-3 text-gray-800 flex items-center gap-2">
              <span className="w-2 h-6 bg-orange-500 rounded"></span>
              Bahan-Bahan
            </h3>
            <ul className="space-y-2">
              {recipe.ingredients.map((ingredient, index) => (
                <li key={index} className="flex items-start gap-3 text-gray-700">
                  <span className="text-orange-500 font-bold mt-1">•</span>
                  <span>{ingredient}</span>
                </li>
              ))}
            </ul>
          </div>

          <div>
            <h3 className="text-xl font-bold mb-3 text-gray-800 flex items-center gap-2">
              <span className="w-2 h-6 bg-orange-500 rounded"></span>
              Cara Membuat
            </h3>
            <ol className="space-y-4">
              {recipe.steps.map((step, index) => (
                <li key={index} className="flex gap-4">
                  <div className="flex-shrink-0 w-8 h-8 bg-orange-500 text-white rounded-full flex items-center justify-center font-bold">
                    {index + 1}
                  </div>
                  <p className="flex-1 text-gray-700 pt-1">{step}</p>
                </li>
              ))}
            </ol>
          </div>
        </div>
      </div>
    </div>
  );

  return (
    <div className="min-h-screen bg-gradient-to-br from-orange-50 via-white to-orange-50">
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700;800&display=swap');
        
        * {
          font-family: 'Poppins', sans-serif;
        }
        
        @keyframes slideUp {
          from {
            opacity: 0;
            transform: translateY(50px);
          }
          to {
            opacity: 1;
            transform: translateY(0);
          }
        }
        
        @keyframes fadeIn {
          from {
            opacity: 0;
          }
          to {
            opacity: 1;
          }
        }
        
        .animate-fade-in {
          animation: fadeIn 0.5s ease-out;
        }
      `}</style>

      {/* Header */}
      <div className="bg-gradient-to-r from-orange-500 to-orange-600 text-white p-6 pb-8 shadow-lg">
        <div className="max-w-6xl mx-auto">
          <div className="flex items-center justify-between mb-6">
            <div className="flex items-center gap-3">
              <div className="bg-white/20 p-3 rounded-2xl backdrop-blur-sm">
                <ChefHat className="w-8 h-8" />
              </div>
              <div>
                <h1 className="text-2xl font-bold">Resepku</h1>
                <p className="text-orange-100 text-sm">Koleksi Resep Nusantara</p>
              </div>
            </div>
            <div className="bg-white/20 p-3 rounded-full backdrop-blur-sm">
              <Book className="w-6 h-6" />
            </div>
          </div>

          {/* Search Bar */}
          <div className="relative">
            <Search className="absolute left-4 top-1/2 transform -translate-y-1/2 text-gray-400 w-5 h-5" />
            <input
              type="text"
              placeholder="Cari resep favorit..."
              value={searchQuery}
              onChange={(e) => setSearchQuery(e.target.value)}
              className="w-full pl-12 pr-4 py-4 rounded-2xl text-gray-800 placeholder-gray-400 focus:outline-none focus:ring-4 focus:ring-orange-300 transition-all"
            />
          </div>
        </div>
      </div>

      {/* Categories */}
      <div className="max-w-6xl mx-auto px-6 py-6">
        <div className="flex gap-3 overflow-x-auto pb-2 scrollbar-hide">
          {categories.map((category) => (
            <button
              key={category}
              className={`px-6 py-2.5 rounded-full font-medium whitespace-nowrap transition-all ${
                category === 'Semua'
                  ? 'bg-orange-500 text-white shadow-lg shadow-orange-200'
                  : 'bg-white text-gray-700 hover:bg-orange-50 border border-gray-200'
              }`}
            >
              {category}
            </button>
          ))}
        </div>
      </div>

      {/* Recipe Grid */}
      <div className="max-w-6xl mx-auto px-6 pb-24">
        {activeTab === 'favorites' && favorites.size === 0 ? (
          <div className="text-center py-16 animate-fade-in">
            <Heart className="w-16 h-16 text-gray-300 mx-auto mb-4" />
            <h3 className="text-xl font-bold text-gray-600 mb-2">Belum Ada Resep Favorit</h3>
            <p className="text-gray-500">Mulai simpan resep favorit Anda dengan menekan ikon hati</p>
          </div>
        ) : (
          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 animate-fade-in">
            {filteredRecipes.map((recipe) => (
              <RecipeCard key={recipe.id} recipe={recipe} />
            ))}
          </div>
        )}
      </div>

      {/* Bottom Navigation */}
      <div className="fixed bottom-0 left-0 right-0 bg-white border-t border-gray-200 px-6 py-4 shadow-2xl">
        <div className="max-w-6xl mx-auto flex justify-around items-center">
          <button
            onClick={() => setActiveTab('home')}
            className={`flex flex-col items-center gap-1 px-4 py-2 rounded-xl transition-all ${
              activeTab === 'home' ? 'text-orange-500 bg-orange-50' : 'text-gray-400 hover:text-gray-600'
            }`}
          >
            <Home className="w-6 h-6" />
            <span className="text-xs font-medium">Beranda</span>
          </button>
          <button
            onClick={() => setActiveTab('favorites')}
            className={`flex flex-col items-center gap-1 px-4 py-2 rounded-xl transition-all relative ${
              activeTab === 'favorites' ? 'text-orange-500 bg-orange-50' : 'text-gray-400 hover:text-gray-600'
            }`}
          >
            <Bookmark className="w-6 h-6" />
            <span className="text-xs font-medium">Favorit</span>
            {favorites.size > 0 && (
              <span className="absolute -top-1 -right-1 bg-red-500 text-white text-xs w-5 h-5 rounded-full flex items-center justify-center">
                {favorites.size}
              </span>
            )}
          </button>
          <button className="flex flex-col items-center gap-1 px-4 py-2 rounded-xl text-gray-400 hover:text-gray-600 transition-all">
            <User className="w-6 h-6" />
            <span className="text-xs font-medium">Profil</span>
          </button>
        </div>
      </div>

      {/* Recipe Detail Modal */}
      {selectedRecipe && <RecipeDetail recipe={selectedRecipe} />}
    </div>
  );
};

export default RecipeApp;
