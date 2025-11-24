===FRONTEND PACKAGE.JSON===
{
  "name": "definitive-word-frontend",
  "version": "1.0.0",
  "description": "The Definitive Word Ministry Platform",
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "next lint"
  },
  "dependencies": {
    "next": "14.0.0",
    "react": "18.2.0",
    "react-dom": "18.2.0",
    "axios": "^1.5.0",
    "react-icons": "^4.11.0",
    "framer-motion": "^10.16.0"
  },
  "devDependencies": {
    "autoprefixer": "^10.4.15",
    "postcss": "^8.4.29",
    "tailwindcss": "^3.3.0",
    "eslint": "^8.48.0",
    "eslint-config-next": "14.0.0"
  }
}

===TAILWIND CONFIG===
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    './pages/**/*.{js,ts,jsx,tsx,mdx}',
    './components/**/*.{js,ts,jsx,tsx,mdx}',
  ],
  theme: {
    extend: {
      colors: {
        prophetic: {
          red: '#C41E3A',
          blue: '#0066CC', 
          gold: '#D4AF37',
          white: '#F8F9FA',
          navy: '#003366',
          lightblue: '#E6F2FF'
        }
      },
      fontFamily: {
        display: ['Playfair Display', 'serif'],
        serif: ['Georgia', 'serif'],
      },
      backgroundImage: {
        'gradient-prophetic': 'linear-gradient(135deg, #C41E3A 0%, #0066CC 50%, #003366 100%)',
        'gradient-gold': 'linear-gradient(135deg, #D4AF37 0%, #F7EF8A 100%)'
      }
    },
  },
  plugins: [],
}

===POSTCSS CONFIG===
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}

===NEXT CONFIG===
/** @type {import('next').NextConfig} */
const nextConfig = {
  reactStrictMode: true,
  swcMinify: true,
}

module.exports = nextConfig

===GLOBAL CSS===
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;600;700&display=swap');

@tailwind base;
@tailwind components;
@tailwind utilities;

:root {
  --font-playfair: 'Playfair Display', serif;
}

@layer base {
  html {
    scroll-behavior: smooth;
  }
  
  body {
    @apply bg-prophetic-white text-prophetic-navy;
    font-family: 'Georgia', serif;
  }
}

@layer components {
  .btn-primary {
    @apply bg-prophetic-red hover:bg-red-700 text-white px-6 py-3 rounded-lg font-semibold transition-all duration-300 transform hover:scale-105;
  }
  
  .btn-secondary {
    @apply border-2 border-prophetic-gold text-prophetic-gold hover:bg-prophetic-gold hover:text-prophetic-navy px-6 py-3 rounded-lg font-semibold transition-all duration-300;
  }
  
  .btn-outline {
    @apply border-2 border-prophetic-blue text-prophetic-blue hover:bg-prophetic-blue hover:text-white px-6 py-3 rounded-lg font-semibold transition-all duration-300;
  }
  
  .card-hover {
    @apply transition-all duration-300 hover:shadow-2xl hover:scale-105;
  }
  
  .section-padding {
    @apply py-16 lg:py-24;
  }
  
  .container-custom {
    @apply max-w-7xl mx-auto px-4 sm:px-6 lg:px-8;
  }
}

/* Custom scrollbar */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  @apply bg-prophetic-lightblue;
}

::-webkit-scrollbar-thumb {
  @apply bg-prophetic-gold rounded-full;
}

::-webkit-scrollbar-thumb:hover {
  @apply bg-prophetic-red;
}

/* Line clamp utilities */
.line-clamp-2 {
  overflow: hidden;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 2;
}

.line-clamp-3 {
  overflow: hidden;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 3;
}

===LAYOUT COMPONENT===
import { useState, useEffect } from 'react'
import Head from 'next/head'
import Link from 'next/link'
import { useRouter } from 'next/router'
import { 
  FiBook, 
  FiUsers, 
  FiHeart, 
  FiUser, 
  FiMenu, 
  FiX,
  FiHome,
  FiSearch
} from 'react-icons/fi'

export default function Layout({ children }) {
  const [isMenuOpen, setIsMenuOpen] = useState(false)
  const [isScrolled, setIsScrolled] = useState(false)
  const router = useRouter()

  useEffect(() => {
    const handleScroll = () => {
      setIsScrolled(window.scrollY > 50)
    }
    window.addEventListener('scroll', handleScroll)
    return () => window.removeEventListener('scroll', handleScroll)
  }, [])

  const navigation = [
    { name: 'Home', href: '/', icon: FiHome },
    { name: 'Library', href: '/library', icon: FiBook },
    { name: 'Study Groups', href: '/groups', icon: FiUsers },
    { name: 'Prayer', href: '/prayer', icon: FiHeart },
    { name: 'My Bookshelf', href: '/bookshelf', icon: FiUser },
  ]

  return (
    <div className="min-h-screen bg-prophetic-white">
      <Head>
        <title>The Definitive Word - Your Destiny Has Been Written</title>
        <meta name="description" content="Prophetic e-books and resources for your spiritual journey" />
        <link rel="icon" href="/favicon.ico" />
      </Head>

      <header className={`fixed w-full z-50 transition-all duration-300 ${
        isScrolled 
          ? 'bg-white/95 backdrop-blur-md shadow-lg border-b border-prophetic-gold/20' 
          : 'bg-transparent'
      }`}>
        <div className="container-custom">
          <div className="flex justify-between items-center h-20">
            <Link href="/" className="flex items-center space-x-3 group">
              <div className="bg-gradient-to-r from-prophetic-red to-prophetic-blue p-3 rounded-xl shadow-lg group-hover:scale-110 transition-transform">
                <FiBook className="w-6 h-6 text-white" />
              </div>
              <div className="text-left">
                <h1 className="text-2xl font-display font-bold text-prophetic-navy group-hover:text-prophetic-red transition-colors">
                  The Definitive Word
                </h1>
                <p className="text-sm text-prophetic-red italic font-medium">
                  Your Destiny Has Been Written
                </p>
              </div>
            </Link>

            <nav className="hidden lg:flex items-center space-x-8">
              {navigation.map((item) => {
                const isActive = router.pathname === item.href
                return (
                  <Link
                    key={item.name}
                    href={item.href}
                    className={`flex items-center space-x-2 font-medium transition-all duration-300 ${
                      isActive
                        ? 'text-prophetic-red border-b-2 border-prophetic-red'
                        : 'text-prophetic-navy hover:text-prophetic-red'
                    }`}
                  >
                    <item.icon className="w-4 h-4" />
                    <span>{item.name}</span>
                  </Link>
                )
              })}
            </nav>

            <div className="hidden lg:flex items-center space-x-4">
              <button className="p-2 text-prophetic-navy hover:text-prophetic-red transition-colors">
                <FiSearch className="w-5 h-5" />
              </button>
              <button className="btn-primary text-sm">
                Sign In
              </button>
            </div>

            <button 
              className="lg:hidden p-2 text-prophetic-navy"
              onClick={() => setIsMenuOpen(!isMenuOpen)}
            >
              {isMenuOpen ? <FiX className="w-6 h-6" /> : <FiMenu className="w-6 h-6" />}
            </button>
          </div>
        </div>

        {isMenuOpen && (
          <div className="lg:hidden bg-white border-t border-prophetic-gold/20 shadow-xl">
            <div className="container-custom py-4">
              <div className="space-y-4">
                {navigation.map((item) => {
                  const isActive = router.pathname === item.href
                  return (
                    <Link
                      key={item.name}
                      href={item.href}
                      className={`flex items-center space-x-3 p-3 rounded-lg transition-all duration-300 ${
                        isActive
                          ? 'bg-prophetic-red text-white'
                          : 'text-prophetic-navy hover:bg-prophetic-lightblue'
                      }`}
                      onClick={() => setIsMenuOpen(false)}
                    >
                      <item.icon className="w-5 h-5" />
                      <span className="font-medium">{item.name}</span>
                    </Link>
                  )
                })}
                <div className="pt-4 border-t border-prophetic-gold/20">
                  <button className="w-full btn-primary">
                    Sign In
                  </button>
                </div>
              </div>
            </div>
          </div>
        )}
      </header>

      <main className="pt-20">
        {children}
      </main>

      <Footer />
    </div>
  )
}

function Footer() {
  return (
    <footer className="bg-prophetic-navy text-white mt-20">
      <div className="container-custom py-16">
        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div className="lg:col-span-2">
            <div className="flex items-center space-x-3 mb-6">
              <div className="bg-prophetic-red p-2 rounded-lg">
                <FiBook className="w-6 h-6 text-white" />
              </div>
              <div>
                <h2 className="text-2xl font-display font-bold">The Definitive Word</h2>
                <p className="text-prophetic-gold font-medium">Your Destiny Has Been Written</p>
              </div>
            </div>
            <p className="text-prophetic-white/80 text-lg leading-relaxed">
              Unlocking prophetic understanding through inspired writings and teachings. 
              Discover your God-given purpose and walk in your ordained destiny.
            </p>
          </div>

          <div>
            <h3 className="text-lg font-semibold mb-6 text-prophetic-gold">Ministry</h3>
            <ul className="space-y-3">
              {['About Us', 'Our Beliefs', 'Leadership', 'Contact', 'Support'].map((item) => (
                <li key={item}>
                  <a href="#" className="text-prophetic-white/80 hover:text-prophetic-gold transition-colors">
                    {item}
                  </a>
                </li>
              ))}
            </ul>
          </div>

          <div>
            <h3 className="text-lg font-semibold mb-6 text-prophetic-gold">Connect</h3>
            <ul className="space-y-3">
              {['Prayer Requests', 'Study Groups', 'Events', 'Newsletter', 'Give'].map((item) => (
                <li key={item}>
                  <a href="#" className="text-prophetic-white/80 hover:text-prophetic-gold transition-colors">
                    {item}
                  </a>
                </li>
              ))}
            </ul>
          </div>
        </div>

        <div className="border-t border-prophetic-white/20 mt-12 pt-8 flex flex-col md:flex-row justify-between items-center">
          <p className="text-prophetic-white/60 text-center md:text-left">
            &copy; 2024 The Definitive Word Ministry. All rights reserved.
          </p>
          <div className="flex space-x-6 mt-4 md:mt-0">
            {['Privacy', 'Terms', 'Cookies'].map((item) => (
              <a key={item} href="#" className="text-prophetic-white/60 hover:text-prophetic-gold transition-colors">
                {item}
              </a>
            ))}
          </div>
        </div>
      </div>
    </footer>
  )
}

===BOOKCARD COMPONENT===
import { motion } from 'framer-motion'
import { FiStar, FiBook, FiUser, FiShoppingCart } from 'react-icons/fi'

export default function BookCard({ book }) {
  const renderStars = (rating) => {
    return Array.from({ length: 5 }, (_, i) => (
      <FiStar
        key={i}
        className={`w-4 h-4 ${
          i < Math.floor(rating) ? 'text-prophetic-gold fill-current' : 'text-gray-300'
        }`}
      />
    ))
  }

  return (
    <motion.div
      whileHover={{ y: -5 }}
      className="bg-white rounded-2xl shadow-lg hover:shadow-2xl transition-all duration-300 overflow-hidden group border border-prophetic-gold/20"
    >
      <div className="relative h-48 bg-gradient-to-br from-prophetic-blue to-prophetic-navy flex items-center justify-center overflow-hidden">
        <div className="absolute inset-0 bg-black/10 group-hover:bg-black/20 transition-colors"></div>
        <FiBook className="w-16 h-16 text-prophetic-gold/60 z-10" />
        
        <div className="absolute top-4 left-4 flex flex-col space-y-2">
          {book.isNew && (
            <span className="bg-prophetic-red text-white px-3 py-1 rounded-full text-xs font-semibold">
              New
            </span>
          )}
          {book.isFeatured && (
            <span className="bg-prophetic-gold text-prophetic-navy px-3 py-1 rounded-full text-xs font-semibold">
              Featured
            </span>
          )}
        </div>
        
        <div className="absolute top-4 right-4 bg-white/20 backdrop-blur-sm text-white px-3 py-1 rounded-full text-sm font-semibold">
          {book.category}
        </div>
      </div>
      
      <div className="p-6">
        <h3 className="text-xl font-display font-bold text-prophetic-navy group-hover:text-prophetic-red transition-colors mb-2 line-clamp-2">
          {book.title}
        </h3>
        
        <div className="flex items-center text-prophetic-blue text-sm mb-3">
          <FiUser className="w-4 h-4 mr-1" />
          <span className="font-medium">{book.author}</span>
        </div>
        
        <p className="text-gray-600 text-sm mb-4 line-clamp-3 leading-relaxed">
          {book.description}
        </p>
        
        <div className="flex items-center justify-between mb-4">
          <div className="flex items-center space-x-1">
            {renderStars(book.rating)}
            <span className="text-sm text-gray-500 ml-1">({book.rating})</span>
          </div>
          <div className="text-sm text-gray-500 flex items-center">
            <FiBook className="w-3 h-3 mr-1" />
            {book.pages} pages
          </div>
        </div>
        
        <div className="flex items-center justify-between">
          <div className="text-2xl font-bold text-prophetic-gold">
            ${book.price}
          </div>
          <div className="flex space-x-2">
            <button className="p-2 text-prophetic-blue hover:bg-prophetic-lightblue rounded-lg transition-colors">
              <FiBook className="w-5 h-5" />
            </button>
            <button className="p-2 bg-prophetic-red hover:bg-red-700 text-white rounded-lg transition-colors">
              <FiShoppingCart className="w-5 h-5" />
            </button>
          </div>
        </div>
      </div>
    </motion.div>
  )
}

===CATEGORYCARD COMPONENT===
import { motion } from 'framer-motion'
import Link from 'next/link'

export default function CategoryCard({ category }) {
  const Icon = category.icon
  
  return (
    <motion.div
      whileHover={{ scale: 1.05 }}
      className="group"
    >
      <Link href={`/library?category=${category.name.toLowerCase()}`}>
        <div className={`bg-gradient-to-br ${category.color} p-8 rounded-2xl text-white text-center shadow-lg hover:shadow-2xl transition-all duration-300 cursor-pointer h-full flex flex-col items-center justify-center min-h-[200px]`}>
          <div className="bg-white/20 p-4 rounded-2xl mb-4 group-hover:scale-110 transition-transform">
            <Icon className="w-8 h-8" />
          </div>
          
          <h3 className="text-xl font-display font-bold mb-2">
            {category.name}
          </h3>
          
          <p className="text-white/90 text-sm mb-3 leading-relaxed">
            {category.description}
          </p>
          
          <div className="text-white/70 text-sm font-medium">
            {category.count} Resources
          </div>
        </div>
      </Link>
    </motion.div>
  )
}

===HOMEPAGE===
import Layout from '../components/Layout'
import BookCard from '../components/BookCard'
import CategoryCard from '../components/CategoryCard'
import { motion } from 'framer-motion'
import { 
  FiArrowRight, 
  FiStar, 
  FiUsers, 
  FiBookOpen,
  FiAward 
} from 'react-icons/fi'

export default function Home() {
  const featuredBooks = [
    {
      id: 1,
      title: "The Prophetic Destiny",
      author: "Dr. Michael Johnson",
      description: "Discover your God-given purpose and walk in your ordained destiny through this comprehensive guide to understanding prophetic calling.",
      price: 24.99,
      category: "Prophetic",
      ministry: "General",
      rating: 4.9,
      pages: 256,
      isFeatured: true,
      isNew: true
    },
    {
      id: 2,
      title: "Prayers That Open Heaven",
      author: "Sarah Williams",
      description: "Learn to pray with authority and see heaven's gates open. Transform your prayer life with these powerful biblical principles.",
      price: 19.99,
      category: "Prayer",
      ministry: "General", 
      rating: 4.8,
      pages: 192,
      isFeatured: true,
      isNew: false
    },
    {
      id: 3,
      title: "Understanding Your Dreams",
      author: "Prophet James Miller",
      description: "Biblical interpretation of dreams and visions for today. Learn to discern God's voice through your nightly visions.",
      price: 29.99,
      category: "Dreams",
      ministry: "General",
      rating: 4.7,
      pages: 320,
      isFeatured: true,
      isNew: true
    }
  ]

  const categories = [
    { 
      name: "Prophetic", 
      count: 12, 
      description: "Understanding God's voice and purpose",
      icon: FiAward,
      color: "from-prophetic-red to-red-600"
    },
    { 
      name: "Prayer", 
      count: 8, 
      description: "Deepening your communication with God",
      icon: FiBookOpen,
      color: "from-prophetic-blue to-blue-600"
    },
    { 
      name: "Dreams & Visions", 
      count: 6, 
      description: "Interpreting spiritual revelations",
      icon: FiStar,
      color: "from-prophetic-gold to-yellow-500"
    },
    { 
      name: "Destiny", 
      count: 10, 
      description: "Discovering your God-given purpose", 
      icon: FiUsers,
      color: "from-prophetic-navy to-blue-800"
    }
  ]

  const stats = [
    { number: '5,000+', label: 'Active Members' },
    { number: '200+', label: 'Prophetic Resources' },
    { number: '50+', label: 'Study Groups' },
    { number: '24/7', label: 'Prayer Support' }
  ]

  return (
    <Layout>
      <section className="relative min-h-screen flex items-center justify-center bg-gradient-to-br from-prophetic-navy via-prophetic-blue to-prophetic-red overflow-hidden">
        <div className="absolute inset-0 bg-black/40"></div>
        <div className="absolute top-0 left-0 w-full h-full">
          <div className="absolute top-20 left-10 w-4 h-4 bg-prophetic-gold rounded-full animate-pulse"></div>
          <div className="absolute top-40 right-20 w-6 h-6 bg-prophetic-gold rounded-full animate-pulse" style={{animationDelay: '1s'}}></div>
          <div className="absolute bottom-20 left-20 w-8 h-8 bg-prophetic-red rounded-full animate-pulse" style={{animationDelay: '2s'}}></div>
          <div className="absolute bottom-40 right-10 w-5 h-5 bg-prophetic-blue rounded-full animate-pulse" style={{animationDelay: '1.5s'}}></div>
        </div>
        
        <div className="relative container-custom text-center text-white z-10">
          <motion.div
            initial={{ opacity: 0, y: 30 }}
            animate={{ opacity: 1, y: 0 }}
            transition={{ duration: 0.8 }}
          >
            <div className="inline-flex items-center space-x-2 bg-prophetic-gold/20 backdrop-blur-sm border border-prophetic-gold/30 text-prophetic-gold px-6 py-3 rounded-full text-sm font-semibold mb-8">
              <FiStar className="w-4 h-4" />
              <span>Prophetic Resources for Your Journey</span>
            </div>
            
            <h1 className="text-5xl md:text-7xl lg:text-8xl font-display font-bold mb-6 leading-tight">
              Your Spiritual{' '}
              <span className="text-transparent bg-clip-text bg-gradient-to-r from-prophetic-gold to-yellow-200">
                Destiny
              </span>
              <br />
              Has Been Written
            </h1>
            
            <p className="text-xl md:text-2xl mb-12 max-w-4xl mx-auto leading-relaxed text-blue-100">
              Access inspired teachings, prophetic insights, and life-changing resources 
              to walk in your God-ordained purpose. Join thousands discovering their divine calling.
            </p>
            
            <div className="flex flex-col sm:flex-row gap-4 justify-center items-center">
              <button className="btn-primary text-lg px-8 py-4 flex items-center space-x-2">
                <span>Explore Prophetic Library</span>
                <FiArrowRight className="w-5 h-5" />
              </button>
              <button className="btn-secondary text-lg px-8 py-4">
                Join Free Study Group
              </button>
            </div>
          </motion.div>
        </div>
        
        <div className="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
          <div className="w-6 h-10 border-2 border-prophetic-gold rounded-full flex justify-center">
            <div className="w-1 h-3 bg-prophetic-gold rounded-full mt-2"></div>
          </div>
        </div>
      </section>

      <section className="section-padding bg-white">
        <div className="container-custom">
          <div className="grid grid-cols-2 lg:grid-cols-4 gap-8">
            {stats.map((stat, index) => (
              <motion.div
                key={stat.label}
                initial={{ opacity: 0, y: 20 }}
                whileInView={{ opacity: 1, y: 0 }}
                transition={{ duration: 0.6, delay: index * 0.1 }}
                className="text-center"
              >
                <div className="text-3xl lg:text-4xl font-display font-bold text-prophetic-red mb-2">
                  {stat.number}
                </div>
                <div className="text-prophetic-navy font-medium">
                  {stat.label}
                </div>
              </motion.div>
            ))}
          </div>
        </div>
      </section>

      <section className="section-padding bg-prophetic-lightblue">
        <div className="container-custom">
          <motion.div
            initial={{ opacity: 0, y: 30 }}
            whileInView={{ opacity: 1, y: 0 }}
            transition={{ duration: 0.8 }}
            className="text-center mb-16"
          >
            <h2 className="text-4xl lg:text-5xl font-display font-bold text-prophetic-navy mb-6">
              Featured Prophetic Resources
            </h2>
            <p className="text-xl text-gray-600 max-w-3xl mx-auto leading-relaxed">
              Carefully selected teachings to guide you in understanding your divine purpose and destiny. 
              Each resource is prayerfully crafted for your spiritual growth.
            </p>
          </motion.div>

          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            {featuredBooks.map((book, index) => (
              <motion.div
                key={book.id}
                initial={{ opacity: 0, y: 30 }}
                whileInView={{ opacity: 1, y: 0 }}
                transition={{ duration: 0.6, delay: index * 0.1 }}
              >
                <BookCard book={book} />
              </motion.div>
            ))}
          </div>

          <div className="text-center mt-12">
            <button className="btn-outline px-8 py-4">
              View All Resources
            </button>
          </div>
        </div>
      </section>

      <section className="section-padding bg-white">
        <div className="container-custom">
          <motion.div
            initial={{ opacity: 0, y: 30 }}
            whileInView={{ opacity: 1, y: 0 }}
            transition={{ duration: 0.8 }}
            className="text-center mb-16"
          >
            <h2 className="text-4xl lg:text-5xl font-display font-bold text-prophetic-navy mb-6">
              Explore by Category
            </h2>
            <p className="text-xl text-gray-600 max-w-2xl mx-auto">
              Find resources tailored to your specific spiritual growth areas and ministry focus
            </p>
          </motion.div>

          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
            {categories.map((category, index) => (
              <motion.div
                key={category.name}
                initial={{ opacity: 0, scale: 0.9 }}
                whileInView={{ opacity: 1, scale: 1 }}
                transition={{ duration: 0.6, delay: index * 0.1 }}
              >
                <CategoryCard category={category} />
              </motion.div>
            ))}
          </div>
        </div>
      </section>

      <section className="section-padding bg-gradient-to-br from-prophetic-red to-prophetic-blue relative overflow-hidden">
        <div className="absolute inset-0 bg-black/20"></div>
        <div className="absolute top-0 right-0 w-64 h-64 bg-prophetic-gold/10 rounded-full -translate-y-32 translate-x-32"></div>
        <div className="absolute bottom-0 left-0 w-96 h-96 bg-prophetic-gold/5 rounded-full -translate-x-48 translate-y-48"></div>
        
        <div className="relative container-custom text-center text-white z-10">
          <motion.div
            initial={{ opacity: 0, y: 30 }}
            whileInView={{ opacity: 1, y: 0 }}
            transition={{ duration: 0.8 }}
          >
            <h2 className="text-4xl lg:text-5xl font-display font-bold mb-6">
              Ready to Discover<br />Your Divine Destiny?
            </h2>
            <p className="text-xl mb-12 max-w-3xl mx-auto text-blue-100 leading-relaxed">
              Join thousands of believers who are walking in their God-given purpose 
              through our prophetic resources and supportive community.
            </p>
            <div className="flex flex-col sm:flex-row gap-4 justify-center items-center">
              <button className="bg-prophetic-gold hover:bg-yellow-500 text-prophetic-navy px-8 py-4 rounded-lg font-semibold text-lg transition-all duration-300 transform hover:scale-105">
                Start Your Journey Today
              </button>
              <button className="border-2 border-white hover:bg-white hover:text-prophetic-blue text-white px-8 py-4 rounded-lg font-semibold text-lg transition-all duration-300">
                Schedule Prayer Session
              </button>
            </div>
          </motion.div>
        </div>
      </section>
    </Layout>
  )
}

===LIBRARY PAGE===
import Layout from '../components/Layout'
import BookCard from '../components/BookCard'
import { useState } from 'react'
import { FiFilter, FiGrid, FiList, FiSearch } from 'react-icons/fi'

export default function Library() {
  const [viewMode, setViewMode] = useState('grid')
  const [selectedCategory, setSelectedCategory] = useState('all')
  const [selectedMinistry, setSelectedMinistry] = useState('all')
  const [searchQuery, setSearchQuery] = useState('')

  const categories = ['All', 'Prophetic', 'Prayer', 'Dreams', 'Destiny', 'Men\'s Ministry', 'Women\'s Ministry', 'Healing', 'Deliverance']
  const ministries = ['All', 'Men', 'Women', 'Youth', 'General']

  const books = [
    {
      id: 1,
      title: "The Prophetic Destiny",
      author: "Dr. Michael Johnson",
      description: "Discover your God-given purpose and walk in your ordained destiny.",
      price: 24.99,
      category: "Prophetic",
      ministry: "General",
      rating: 4.9,
      pages: 256,
      isFeatured: true,
      isNew: true
    },
    {
      id: 2,
      title: "Prayers That Open Heaven",
      author: "Sarah Williams",
      description: "Learn to pray with authority and see heaven's gates open.",
      price: 19.99,
      category: "Prayer",
      ministry: "General", 
      rating: 4.8,
      pages: 192,
      isFeatured: true,
      isNew: false
    },
    {
      id: 3,
      title: "Understanding Your Dreams",
      author: "Prophet James Miller",
      description: "Biblical interpretation of dreams and visions for today.",
      price: 29.99,
      category: "Dreams",
      ministry: "General",
      rating: 4.7,
      pages: 320,
      isFeatured: true,
      isNew: true
    },
    {
      id: 4,
      title: "Mighty Man of Valor",
      author: "Pastor Robert King",
      description: "A man's guide to spiritual warfare and kingdom leadership.",
      price: 22.99,
      category: "Men's Ministry",
      ministry: "Men",
      rating: 4.9,
      pages: 280,
      isFeatured: false,
      isNew: true
    },
    {
      id: 5,
      title: "Virtuous Woman of God",
      author: "Dr. Elizabeth Grace",
      description: "Embracing your identity and purpose as a woman of God.",
      price: 21.99,
      category: "Women's Ministry",
      ministry: "Women",
      rating: 4.8,
      pages: 240,
      isFeatured: false,
      isNew: true
    },
    {
      id: 6,
      title: "Divine Healing Power",
      author: "Apostle Mark Stevens",
      description: "Understanding and operating in God's healing anointing.",
      price: 26.99,
      category: "Healing",
      ministry: "General",
      rating: 4.6,
      pages: 300,
      isFeatured: false,
      isNew: false
    }
  ]

  const filteredBooks = books.filter(book => {
    const matchesCategory = selectedCategory === 'all' || book.category === selectedCategory
    const matchesMinistry = selectedMinistry === 'all' || book.ministry === selectedMinistry
    const matchesSearch = book.title.toLowerCase().includes(searchQuery.toLowerCase()) || 
                         book.author.toLowerCase().includes(searchQuery.toLowerCase())
    return matchesCategory && matchesMinistry && matchesSearch
  })

  return (
    <Layout>
      <div className="section-padding bg-prophetic-white">
        <div className="container-custom">
          <div className="text-center mb-12">
            <h1 className="text-4xl lg:text-5xl font-display font-bold text-prophetic-navy mb-4">
              Prophetic Library
            </h1>
            <p className="text-xl text-gray-600 max-w-2xl mx-auto">
              Explore our collection of inspired teachings and resources for your spiritual journey
            </p>
          </div>

          <div className="bg-white rounded-2xl shadow-lg p-6 mb-8">
            <div className="flex flex-col lg:flex-row gap-4 items-center justify-between">
              <div className="relative flex-1 w-full">
                <FiSearch className="absolute left-4 top-1/2 transform -translate-y-1/2 text-gray-400 w-5 h-5" />
                <input
                  type="text"
                  placeholder="Search books, authors, or topics..."
                  className="w-full pl-12 pr-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-prophetic-blue focus:border-transparent"
                  value={searchQuery}
                  onChange={(e) => setSearchQuery(e.target.value)}
                />
              </div>

              <div className="flex items-center space-x-2 bg-prophetic-lightblue p-1 rounded-lg">
                <button
                  onClick={() => setViewMode('grid')}
                  className={`p-2 rounded-md transition-colors ${
                    viewMode === 'grid' ? 'bg-white shadow-sm' : 'text-gray-600'
                  }`}
                >
                  <FiGrid className="w-5 h-5" />
                </button>
                <button
                  onClick={() => setViewMode('list')}
                  className={`p-2 rounded-md transition-colors ${
                    viewMode === 'list' ? 'bg-white shadow-sm' : 'text-gray-600'
                  }`}
                >
                  <FiList className="w-5 h-5" />
                </button>
              </div>
            </div>

            <div className="grid grid-cols-1 md:grid-cols-2 gap-4 mt-6">
              <div>
                <label className="block text-sm font-medium text-gray-700 mb-2">
                  Category
                </label>
                <select
                  className="w-full border border-gray-300 rounded-lg px-4 py-2 focus:ring-2 focus:ring-prophetic-blue focus:border-transparent"
                  value={selectedCategory}
                  onChange={(e) => setSelectedCategory(e.target.value)}
                >
                  {categories.map(category => (
                    <option key={category} value={category === 'All' ? 'all' : category}>
                      {category}
                    </option>
                  ))}
                </select>
              </div>

              <div>
                <label className="block text-sm font-medium text-gray-700 mb-2">
                  Ministry
                </label>
                <select
                  className="w-full border border-gray-300 rounded-lg px-4 py-2 focus:ring-2 focus:ring-prophetic-blue focus:border-transparent"
                  value={selectedMinistry}
                  onChange={(e) => setSelectedMinistry(e.target.value)}
                >
                  {ministries.map(ministry => (
                    <option key={ministry} value={ministry === 'All' ? 'all' : ministry}>
                      {ministry}
                    </option>
                  ))}
                </select>
              </div>
            </div>
          </div>

          <div className="flex items-center justify-between mb-6">
            <p className="text-gray-600">
              Showing {filteredBooks.length} of {books.length} resources
            </p>
          </div>

          <div className={`grid gap-8 ${
            viewMode === 'grid' 
              ? 'grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4'
              : 'grid-cols-1'
          }`}>
            {filteredBooks.map((book, index) => (
              <BookCard key={book.id} book={book} />
            ))}
          </div>

          {filteredBooks.length === 0 && (
            <div className="text-center py-16">
              <FiSearch className="w-16 h-16 text-gray-300 mx-auto mb-4" />
              <h3 className="text-xl font-semibold text-gray-600 mb-2">
                No resources found
              </h3>
              <p className="text-gray-500">
                Try adjusting your search or filters to find what you're looking for.
              </p>
            </div>
          )}
        </div>
      </div>
    </Layout>
  )
}

===BACKEND PACKAGE.JSON===
{
  "name": "definitive-word-backend",
  "version": "1.0.0",
  "description": "Backend for The Definitive Word Ministry Platform",
  "main": "server.js",
  "scripts": {
    "start": "node server.js",
    "dev": "nodemon server.js",
    "test": "jest"
  },
  "dependencies": {
    "express": "^4.18.2",
    "mongoose": "^7.5.0",
    "cors": "^2.8.5",
    "dotenv": "^16.3.1",
    "bcryptjs": "^2.4.3",
    "jsonwebtoken": "^9.0.2",
    "multer": "^1.4.5-lts.1",
    "stripe": "^13.3.0",
    "helmet": "^7.0.0",
    "express-rate-limit": "^7.1.0",
    "validator": "^13.11.0",
    "nodemailer": "^6.9.4"
  },
  "devDependencies": {
    "nodemon": "^3.0.1",
    "jest": "^29.6.0"
  },
  "keywords": ["ministry", "e-books", "prophetic", "christian"],
  "author": "The Definitive Word Ministry",
  "license": "MIT"
}

===BACKEND ENV FILE===
NODE_ENV=development
PORT=5000
FRONTEND_URL=http://localhost:3000
MONGODB_URI=mongodb://localhost:27017/definitive-word
JWT_SECRET=your-super-secret-jwt-key-here-change-in-production

===BACKEND SERVER===
const express = require('express')
const mongoose = require('mongoose')
const cors = require('cors')
const helmet = require('helmet')
const rateLimit = require('express-rate-limit')
require('dotenv').config()

const app = express()

app.use(helmet())
app.use(cors({
  origin: process.env.FRONTEND_URL || 'http://localhost:3000',
  credentials: true
}))

const limiter = rateLimit({
  windowMs: 15 * 60 * 1000,
  max: 100
})
app.use(limiter)

app.use(express.json({ limit: '10mb' }))
app.use(express.urlencoded({ extended: true }))

mongoose.connect(process.env.MONGODB_URI || 'mongodb://localhost:27017/definitive-word', {
  useNewUrlParser: true,
  useUnifiedTopology: true,
})
.then(() => console.log('✅ Connected to MongoDB'))
.catch(err => console.error('❌ MongoDB connection error:', err))

app.use('/api/auth', require('./routes/auth'))
app.use('/api/books', require('./routes/books'))

app.get('/health', (req, res) => {
  res.json({ 
    status: 'OK', 
    message: 'The Definitive Word API is running',
    timestamp: new Date().toISOString()
  })
})

app.use('*', (req, res) => {
  res.status(404).json({
    success: false,
    message: 'Route not found'
  })
})

app.use((error, req, res, next) => {
  console.error('Error:', error)
  res.status(500).json({
    success: false,
    message: 'Internal server error',
    error: process.env.NODE_ENV === 'development' ? error.message : undefined
  })
})

const PORT = process.env.PORT || 5000

app.listen(PORT, () => {
  console.log('🚀 The Definitive Word Ministry Platform Backend')
  console.log(`📍 Server running on port ${PORT}`)
  console.log(`🌐 Environment: ${process.env.NODE_ENV || 'development'}`)
  console.log(`📚 API URL: http://localhost:${PORT}`)
})

===BOOK MODEL===
const mongoose = require('mongoose')

const bookSchema = new mongoose.Schema({
  title: {
    type: String,
    required: [true, 'Book title is required'],
    trim: true,
    maxlength: [200, 'Title cannot exceed 200 characters']
  },
  author: {
    type: String,
    required: [true, 'Author name is required'],
    trim: true
  },
  description: {
    type: String,
    required: [true, 'Description is required'],
    maxlength: [1000, 'Description cannot exceed 1000 characters']
  },
  content: {
    type: String,
    required: true
  },
  price: {
    type: Number,
    required: true,
    min: [0, 'Price cannot be negative']
  },
  category: {
    type: String,
    required: true,
    enum: [
      'Prophetic',
      'Prayer', 
      'Dreams',
      'Destiny',
      'Healing',
      'Deliverance',
      'Men\'s Ministry',
      'Women\'s Ministry',
      'Youth',
      'Leadership'
    ]
  },
  ministry: {
    type: String,
    required: true,
    enum: ['Men', 'Women', 'Youth', 'General']
  },
  tags: [{
    type: String,
    trim: true
  }],
  featured: {
    type: Boolean,
    default: false
  },
  isNew: {
    type: Boolean,
    default: false
  },
  rating: {
    type: Number,
    default: 0,
    min: 0,
    max: 5
  },
  ratingsCount: {
    type: Number,
    default: 0
  },
  pages: {
    type: Number,
    required: true
  },
  downloads: {
    type: Number,
    default: 0
  },
  coverImage: {
    type: String,
    default: ''
  },
  sampleContent: {
    type: String,
    default: ''
  },
  status: {
    type: String,
    enum: ['draft', 'published', 'archived'],
    default: 'published'
  },
  createdBy: {
    type: mongoose.Schema.Types.ObjectId,
    ref: 'User',
    required: true
  }
}, {
  timestamps: true
})

bookSchema.index({ 
  title: 'text', 
  author: 'text', 
  description: 'text',
  tags: 'text'
})

module.exports = mongoose.model('Book', bookSchema)

===USER MODEL===
const mongoose = require('mongoose')
const bcrypt = require('bcryptjs')

const userSchema = new mongoose.Schema({
  email: {
    type: String,
    required: [true, 'Email is required'],
    unique: true,
    lowercase: true,
    trim: true
  },
  password: {
    type: String,
    required: [true, 'Password is required'],
    minlength: [6, 'Password must be at least 6 characters']
  },
  name: {
    type: String,
    required: [true, 'Name is required'],
    trim: true,
    maxlength: [100, 'Name cannot exceed 100 characters']
  },
  avatar: {
    type: String,
    default: ''
  },
  ministryRole: {
    type: String,
    enum: ['Member', 'Leader', 'Minister', 'Admin'],
    default: 'Member'
  },
  gender: {
    type: String,
    enum: ['Male', 'Female', 'Other'],
    required: true
  },
  bookshelf: [{
    book: {
      type: mongoose.Schema.Types.ObjectId,
      ref: 'Book'
    },
    progress: {
      type: Number,
      default: 0,
      min: 0,
      max: 100
    },
    lastRead: {
      type: Date,
      default: Date.now
    },
    notes: [{
      content: String,
      position: String,
      createdAt: {
        type: Date,
        default: Date.now
      }
    }],
    isFavorite: {
      type: Boolean,
      default: false
    },
    addedAt: {
      type: Date,
      default: Date.now
    }
  }],
  readingStats: {
    totalBooks: {
      type: Number,
      default: 0
    },
    totalReadingTime: {
      type: Number,
      default: 0
    },
    currentStreak: {
      type: Number,
      default: 0
    }
  },
  isEmailVerified: {
    type: Boolean,
    default: false
  },
  lastLogin: {
    type: Date
  }
}, {
  timestamps: true
})

userSchema.pre('save', async function(next) {
  if (!this.isModified('password')) return next()
  
  try {
    const salt = await bcrypt.genSalt(12)
    this.password = await bcrypt.hash(this.password, salt)
    next()
  } catch (error) {
    next(error)
  }
})

userSchema.methods.comparePassword = async function(candidatePassword) {
  return await bcrypt.compare(candidatePassword, this.password)
}

module.exports = mongoose.model('User', userSchema)

===AUTH ROUTES===
const express = require('express')
const jwt = require('jsonwebtoken')
const User = require('../models/User')
const auth = require('../middleware/auth')
const router = express.Router()

router.post('/register', async (req, res) => {
  try {
    const { email, password, name, gender } = req.body

    const existingUser = await User.findOne({ email })
    if (existingUser) {
      return res.status(400).json({
        success: false,
        message: 'User already exists with this email'
      })
    }

    const user = new User({
      email,
      password,
      name,
      gender
    })

    await user.save()

    const token = jwt.sign(
      { userId: user._id },
      process.env.JWT_SECRET || 'definitive-word-secret',
      { expiresIn: '7d' }
    )

    res.status(201).json({
      success: true,
      data: {
        user: {
          id: user._id,
          email: user.email,
          name: user.name,
          ministryRole: user.ministryRole,
          avatar: user.avatar
        },
        token
      },
      message: 'User registered successfully'
    })
  } catch (error) {
    console.error('Registration error:', error)
    res.status(400).json({
      success: false,
      message: error.message
    })
  }
})

router.post('/login', async (req, res) => {
  try {
    const { email, password } = req.body

    const user = await User.findOne({ email })
    if (!user) {
      return res.status(401).json({
        success: false,
        message: 'Invalid email or password'
      })
    }

    const isMatch = await user.comparePassword(password)
    if (!isMatch) {
      return res.status(401).json({
        success: false,
        message: 'Invalid email or password'
      })
    }

    user.lastLogin = new Date()
    await user.save()

    const token = jwt.sign(
      { userId: user._id },
      process.env.JWT_SECRET || 'definitive-word-secret',
      { expiresIn: '7d' }
    )

    res.json({
      success: true,
      data: {
        user: {
          id: user._id,
          email: user.email,
          name: user.name,
          ministryRole: user.ministryRole,
          avatar: user.avatar
        },
        token
      },
      message: 'Login successful'
    })
  } catch (error) {
    console.error('Login error:', error)
    res.status(500).json({
      success: false,
      message: 'Error during login'
    })
  }
})

router.get('/me', auth, async (req, res) => {
  try {
    const user = await User.findById(req.user.id)
      .select('-password')
      .populate('bookshelf.book')

    res.json({
      success: true,
      data: user
    })
  } catch (error) {
    console.error('Get user error:', error)
    res.status(500).json({
      success: false,
      message: 'Error fetching user data'
    })
  }
})

module.exports = router

===BOOKS ROUTES===
const express = require('express')
const Book = require('../models/Book')
const auth = require('../middleware/auth')
const router = express.Router()

router.get('/', async (req, res) => {
  try {
    const {
      category,
      ministry,
      featured,
      search,
      page = 1,
      limit = 12,
      sort = 'createdAt'
    } = req.query

    const filter = { status: 'published' }
    
    if (category && category !== 'all') filter.category = category
    if (ministry && ministry !== 'all') filter.ministry = ministry
    if (featured === 'true') filter.featured = true

    const skip = (page - 1) * limit

    let sortObj = {}
    if (sort === 'title') sortObj.title = 1
    else if (sort === 'price') sortObj.price = 1
    else if (sort === 'rating') sortObj.rating = -1
    else sortObj.createdAt = -1

    let query = Book.find(filter)
    if (search) {
      query = Book.find({
        ...filter,
        $text: { $search: search }
      })
    }

    const books = await query
      .sort(sortObj)
      .skip(skip)
      .limit(parseInt(limit))
      .populate('createdBy', 'name')

    const total = await Book.countDocuments(filter)

    res.json({
      success: true,
      data: books,
      pagination: {
        page: parseInt(page),
        limit: parseInt(limit),
        total,
        pages: Math.ceil(total / limit)
      }
    })
  } catch (error) {
    console.error('Get books error:', error)
    res.status(500).json({
      success: false,
      message: 'Error fetching books'
    })
  }
})

router.get('/:id', async (req, res) => {
  try {
    const book = await Book.findById(req.params.id)
      .populate('createdBy', 'name avatar')
    
    if (!book) {
      return res.status(404).json({
        success: false,
        message: 'Book not found'
      })
    }

    res.json({
      success: true,
      data: book
    })
  } catch (error) {
    console.error('Get book error:', error)
    res.status(500).json({
      success: false,
      message: 'Error fetching book'
    })
  }
})

module.exports = router

===AUTH MIDDLEWARE===
const jwt = require('jsonwebtoken')
const User = require('../models/User')

const auth = async (req, res, next) => {
  try {
    const token = req.header('Authorization')?.replace('Bearer ', '')
    
    if (!token) {
      return res.status(401).json({
        success: false,
        message: 'No token provided'
      })
    }

    const decoded = jwt.verify(token, process.env.JWT_SECRET || 'definitive-word-secret')
    const user = await User.findById(decoded.userId).select('-password')
    
    if (!user) {
      return res.status(401).json({
        success: false,
        message: 'Token is invalid'
      })
    }

    req.user = user
    next()
  } catch (error) {
    console.error('Auth middleware error:', error)
    res.status(401).json({
      success: false,
      message: 'Token is invalid'
    })
  }
}

module.exports = auth
<!DOCTYPE html>
<html>
<head>
    <title>Code Splitter</title>
    <style>
        body { font-family: Arial; padding: 20px; }
        textarea { width: 100%; height: 300px; margin: 10px 0; }
        button { padding: 10px 20px; margin: 5px; }
        .file { background: #f0f0f0; padding: 10px; margin: 10px 0; }
    </style>
</head>
<body>
    <h2>Paste ALL Code Here:</h2>
    <textarea id="allCode" placeholder="Paste the entire code here..."></textarea>
    <br>
    <button onclick="splitCode()">Split into Files</button>
    <div id="files"></div>

    <script>
    function splitCode() {
        const allCode = document.getElementById('allCode').value;
        const files = {};
        let currentFile = '';
        let currentContent = [];
        
        const lines = allCode.split('\n');
        
        lines.forEach(line => {
            if (line.startsWith('===') && line.endsWith('===')) {
                if (currentFile) {
                    files[currentFile] = currentContent.join('\n');
                }
                currentFile = line.replace(/===/g, '').trim();
                currentContent = [];
            } else {
                currentContent.push(line);
            }
        });
        
        if (currentFile) {
            files[currentFile] = currentContent.join('\n');
        }
        
        displayFiles(files);
    }
    
    function displayFiles(files) {
        const container = document.getElementById('files');
        container.innerHTML = '<h3>Copy each section to its file:</h3>';
        
        for (const [filename, content] of Object.entries(files)) {
            const fileDiv = document.createElement('div');
            fileDiv.className = 'file';
            fileDiv.innerHTML = `
                <strong>${filename}</strong>
                <button onclick="copyText('${filename}')">Copy</button>
                <pre>${content}</pre>
            `;
            container.appendChild(fileDiv);
        }
    }
    
    function copyText(filename) {
        const content = document.querySelector(`strong:contains("${filename}")`).nextElementSibling.nextElementSibling.textContent;
        navigator.clipboard.writeText(content).then(() => {
            alert(`Copied ${filename}!`);
        });
    }
    </script>
</body>
</html>
