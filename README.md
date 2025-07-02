
import React from 'react';
import { ArrowRight, Calendar, MapPin, Users } from 'lucide-react';

const Albums = () => {
  const albums = [
    {
      id: 1,
      title: "Wedding Ceremonies",
      description: "Capturing the magic of your special day with romantic and timeless photography",
      image: "https://images.unsplash.com/photo-1519741497674-611481863552?auto=format&fit=crop&w=800&h=600",
      stats: { events: 50, photos: 2500, locations: 15 },
      color: "from-pink-500 to-rose-500"
    },
    {
      id: 2,
      title: "Portrait Sessions",
      description: "Professional portraits that showcase your personality and natural beauty",
      image: "https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&w=800&h=600",
      stats: { events: 120, photos: 1800, locations: 8 },
      color: "from-rose-500 to-pink-600"
    },
    {
      id: 3,
      title: "Family Gatherings",
      description: "Heartwarming moments with your loved ones preserved for generations",
      image: "https://images.unsplash.com/photo-1511895426328-dc8714efa430?auto=format&fit=crop&w=800&h=600",
      stats: { events: 80, photos: 3200, locations: 12 },
      color: "from-pink-600 to-rose-600"
    }
  ];

  return (
    <section className="py-20 bg-gradient-to-b from-white to-pink-50">
      <div className="container mx-auto px-6">
        {/* Header */}
        <div className="text-center mb-16">
          <h2 className="text-4xl md:text-5xl font-bold text-gray-800 mb-6">
            Event <span className="bg-gradient-to-r from-pink-500 to-rose-500 bg-clip-text text-transparent">Albums</span>
          </h2>
          <p className="text-xl text-gray-600 max-w-2xl mx-auto">
            Explore my curated collections of life's most precious moments, each telling a unique story
          </p>
        </div>

        {/* Albums Grid */}
        <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-8 max-w-7xl mx-auto">
          {albums.map((album, index) => (
            <div
              key={album.id}
              className="group relative bg-white rounded-3xl overflow-hidden shadow-lg hover:shadow-2xl transition-all duration-500 transform hover:-translate-y-2"
            >
              {/* Image */}
              <div className="relative h-64 overflow-hidden">
                <img
                  src={album.image}
                  alt={album.title}
                  className="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700"
                />
                <div className={`absolute inset-0 bg-gradient-to-t ${album.color} opacity-20 group-hover:opacity-30 transition-opacity duration-300`}></div>
                
                {/* Floating stats */}
                <div className="absolute top-4 right-4 bg-white/90 backdrop-blur-sm rounded-full px-3 py-1">
                  <span className="text-sm font-semibold text-gray-700">{album.stats.photos} Photos</span>
                </div>
              </div>

              {/* Content */}
              <div className="p-6">
                <h3 className="text-2xl font-bold text-gray-800 mb-3 group-hover:text-pink-600 transition-colors duration-300">
                  {album.title}
                </h3>
                <p className="text-gray-600 mb-4 leading-relaxed">
                  {album.description}
                </p>

                {/* Stats */}
                <div className="flex items-center justify-between text-sm text-gray-500 mb-6">
                  <div className="flex items-center space-x-1">
                    <Calendar className="w-4 h-4" />
                    <span>{album.stats.events} Events</span>
                  </div>
                  <div className="flex items-center space-x-1">
                    <MapPin className="w-4 h-4" />
                    <span>{album.stats.locations} Locations</span>
                  </div>
                </div>

                {/* CTA Button */}
                <button className={`w-full bg-gradient-to-r ${album.color} text-white py-3 rounded-xl font-semibold hover:shadow-lg transform hover:scale-105 transition-all duration-300 flex items-center justify-center space-x-2 group-hover:shadow-pink-500/25`}>
                  <span>View Gallery</span>
                  <ArrowRight className="w-4 h-4 group-hover:translate-x-1 transition-transform duration-300" />
                </button>
              </div>
            </div>
          ))}
        </div>

        {/* Bottom CTA */}
        <div className="text-center mt-16">
          <p className="text-gray-600 mb-6">Want to see more of my work?</p>
          <button className="bg-gradient-to-r from-pink-500 to-rose-500 text-white px-8 py-4 rounded-full text-lg font-semibold hover:from-pink-600 hover:to-rose-600 transform hover:scale-105 transition-all duration-300 shadow-lg hover:shadow-xl">
            Browse All Albums
          </button>
        </div>
      </div>
    </section>
  );
};

export default Albums;
